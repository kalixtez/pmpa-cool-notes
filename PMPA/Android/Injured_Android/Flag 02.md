The hint text for flag 2 reads as follows:

`There is a way to bypass the main activity and invoke other activities that are exported.`

From the Android documentation, we know that `Activity` components can be exported. This means that they can be started by other components from external applications. From the Android documentation:

```
android:exported

Whether the activity can be launched by components of other applications:

- If "true", the activity is accessible to any app, and is launchable by its exact class name.
- If "false", the activity can be launched only by components of the same application, applications with the same user ID, or privileged system components. This is the default value when there are no intent filters.
```

One can use `adb` like this to launch the application's activity:

`am start b3nac.injuredandroid/.b25lActivity` this will launch the activity (and the app, if not already open), revealing a view that contains the second flag:

`S3c0nd_F1ag`