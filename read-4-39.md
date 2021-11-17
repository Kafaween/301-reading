# Amplify and Kinesis
* The Analytics category enables you to collect analytics data for your App.
## Set up Analytics backend
1. run in the terminal amplify add analytics
2. selcet :
? Select an Analytics provider (Use arrow keys)
    `Amazon Pinpoint`
? Provide your pinpoint resource name:
    `yourPinpointResourceName`
? Apps need authorization to send analytics events. Do you want to allow guests and unauthenticated users to send analytics events? (we recommend you allow this when getting started)
    `Yes`
3. amplify push
4. add these dependencies :
dependencies {
    // Add these lines in `dependencies`
    implementation 'com.amplifyframework:aws-analytics-pinpoint:1.24.0'
    implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
}
5. make sync
6. add :
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
## Record events

```AnalyticsEvent event = AnalyticsEvent.builder()
    .name("PasswordReset")
    .addProperty("Channel", "SMS")
    .addProperty("Successful", true)
    .addProperty("ProcessDuration", 792)
    .addProperty("UserAge", 120.3)
    .build();

Amplify.Analytics.recordEvent(event);
```

## View Analytics console by using : 
amplify console analytics
