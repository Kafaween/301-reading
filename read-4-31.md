# Espresso

## Create UI tests with Espresso Test Recorder 

The Espresso Test Recorder tool lets you create UI tests for your app without writing any test code. By recording a test scenario, you can record your interactions with a device and add assertions to verify UI elements in particular snapshots of your app.

Espresso Test Recorder then takes the saved recording and automatically generates a corresponding UI test that you can run to test your app.

The Espresso API encourages you to create concise and reliable UI tests based on user actions.

## Record an Espresso test

Espresso tests consist of two primary components: UI interactions and assertions on View elements. UI interactions include tap and type actions that a person may use to interact with your app. Assertions verify the existence or contents of visual elements on the screen.

## Record UI interactions

To start recording a test with Espresso Test Recorder, proceed as follows: 


    1. Click Run > Record Espresso Test.
    2. In the Select Deployment Target window, choose the device on which you want to record the test. If necessary, create a new Android Virtual Device. Click OK.
    3. Espresso Test Recorder triggers a build of your project, and the app must install and launch before Espresso Test Recorder allows you to interact with it. The Record Your Test window appears after the app launches, and since you have not interacted with the device yet, the main panel reads "No events recorded yet." Interact with your device to start logging events such as "tap" and "type" actions.

## The following code snippet shows an example of an Espresso test:

```
@Test
fun greeterSaysHello() {
    onView(withId(R.id.name_field)).perform(typeText("Steve"))
    onView(withId(R.id.greet_button)).perform(click())
    onView(withText("Hello Steve!")).check(matches(isDisplayed()))
}
```

