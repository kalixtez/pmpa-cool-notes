An Android application is divided in 4 types of components:

* `Activity`:
		This is the category for normal user "views" or interfaces. Components of this type will render buttons, menus, and other type of interactable UI elements that the user will directly see and use.
* `Service
		The service component is used for tasks that the application is usually performing in the background without user intervention. 
* `ContentProvider`
		The ContentProvider type of component is an entry point for external applications to consume data from the application that implements it. If an application wishes to expose data, it implements a `ContentProvider`.
* `BroadcastReceiver`
		Finally, the BroadcastReceiver component enables the converse operation. If an application wishes to receive messages/notifications from external applications and trigger an event in response to them, it implements a BroadcastReceiver as means of inter-process communication.

## Android Manifest

The AndroidManifest.xml file is a configuration file present in **all** Android apps. As stated in the official documentation:

```
Every app project must have an `AndroidManifest.xml` file, with precisely that name, at the root of the [project source set](https://developer.android.com/studio/build#sourcesets). The manifest file describes essential information about your app to the Android build tools, the Android operating system, and Google Play.
```

It is more or less akin to the META-INF/MANIFEST.MF that's packed along `jar` Java applications, and describes multiple aspects of the application, such as declaration of the SDK, declaration of which hardware and software permissions the app will require to run, which **components** there exist in the app (components are the building block of Android apps).

## Intents

The modular architecture of Android apps allow for a clear flow of interoperation in the form of `Intents`.  Intents allow for an app to launch the components of another app. Intents define `Action`, `Data`, `Category`, `Extra` and `Flags` fields, that specify how the receiving app will handle the startup of the requested activity.

Depending on whether they declare a specific target to handle the request, Intents can be **explicit** or **implicit**. The only difference being that implicit intents just specify an `Action` and let the system handle the search of an application that has a suitable component, using an `Intent filter` (declared in the AndroidManifest) of the application. This intent filter will specify what kind of actions, data, etc... it can handle and if a match is found the system will launch it to handle the implicit intent.

```xml
<intent-filter android:[icon](https://developer.android.com/guide/topics/manifest/intent-filter-element#icon)="_drawable resource_"
               android:[label](https://developer.android.com/guide/topics/manifest/intent-filter-element#label)="_string resource_"
               android:[priority](https://developer.android.com/guide/topics/manifest/intent-filter-element#priority)="_integer_" >
    ...
</intent-filter>
```

### Parcelable objects

Objects can be passed as `Extras` through an `Intent`, from an activity to another, if:

1. The object's class is in both classpaths of each app.
2. The object implements the `Parcelable` interface.

`Intent` objects themselves are parcelable, which means an Intent object can be passed as the `Extra` of another Intent. This is how flag 12 puzzle is solved.