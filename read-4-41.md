# Intent Filters

### Allowing Other Apps to Start Your Activity

- if you build a social app that can share messages or photos with the user's friends, you should support the ACTION_SEND intent.
- Then, when users initiate a "share" action from another app, your app appears as an option in the chooser dialog

## To allow other apps to start your activity in this way :

- you need to add an <intent-filter> element in your manifest file for the corresponding <activity> element.
- The system may send a given Intent to an activity if that activity has an intent filter fulfills the following criteria of the Intent object:

1. Action : Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.
2. Data : A description of the data associated with the intent.
3. Category : usually related to the user gesture or location from which it's started ,all implicit intents are defined with CATEGORY_DEFAULT by default.

- For example

```<activity android:name="ShareActivity">
    <intent-filter>
        <action android:name="android.intent.action.SEND"/>
        <category android:name="android.intent.category.DEFAULT"/>
        <data android:mimeType="text/plain"/>
        <data android:mimeType="image/*"/>
    </intent-filter>
   </activity>
   
```

## Handle the Intent in Your Activity

- call getIntent() to retrieve the Intent that started the activity. , but you should generally do so during early callbacks such as onCreate() or onStart().

```@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    setContentView(R.layout.main);

    // Get the intent that started this activity
    Intent intent = getIntent();
    Uri data = intent.getData();

    // Figure out what to do based on the intent type
    if (intent.getType().indexOf("image/") != -1) {
        // Handle intents with image data ...
    } else if (intent.getType().equals("text/plain")) {
        // Handle intents with text ...
    }
}

```
