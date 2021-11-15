# SNS: Getting Started
Step 1: Create a topic
1. Sign in to the Amazon SNS console.
2. In the left navigation pane, choose Topics.
3. On the Topics page, choose Create topic.
4. By default, the console creates a FIFO topic. Choose Standard.
5. In the Details section, enter a Name for the topic, such as MyTopic.
6. Scroll to the end of the form and choose Create topic.
7. The console opens the new topic's Details page.

Step 2: Create a subscription to the topic
Step 3: Publish a message to the topic
Step 4: Delete the subscription and topic
# SNS with Amplify (and Firebase)
* Enable your users to receive mobile push messages sent from the Apple (APNs) and Google (FCM/GCM) platforms.
* The CLI deploys your push notification backend using Amazon Pinpoint
1.  add the SDK to your app.

```cd ./YOUR_PROJECT_FOLDER
amplify add notifications
```

2. Choose Firebase Cloud Messaging (FCM).
> FCM
3. Add the following dependencies and plugin to your app/build.gradle:

```dependencies {
    // Overrides an auth dependency to ensure correct behavior
    implementation 'com.google.android.gms:play-services-auth:19.2.0'

    // Import the BoM for the Firebase platform
    implementation platform('com.google.firebase:firebase-bom:28.2.1')
    implementation 'com.google.firebase:firebase-messaging'

    implementation 'com.amazonaws:aws-android-sdk-pinpoint:2.25.+'
    implementation ('com.amazonaws:aws-android-sdk-mobile-client:2.26.+@aar') { transitive = true }
}

apply plugin: 'com.google.gms.google-services'
```

4. Add the following to your project level build.gradle:

```
buildscript {
    dependencies {
        classpath 'com.google.gms:google-services:4.0.1'
    }
}

allprojects {
    repositories {
        google()
    }
}
```
5. added this tag to AndroidManifest.xml:

```<service
    android:name=".PushListenerService">
    <intent-filter>
        <action android:name="com.google.firebase.MESSAGING_EVENT"/>
    </intent-filter>
</service>
```
