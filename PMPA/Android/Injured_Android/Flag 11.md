For flag 11, we need to trigger a component of the application, using an implicit intent, to browse a URL. This is done as follows:

`am start -a android.intent.action.VIEW -d "flag11://"`

It can also be explicit, like this:

`am start -n "b3nac.injuredandroid/.DeepLinkActivity" -a android.intent.action.VIEW -d "flag11://"`

But it isn't necessary. This can all be deduced from the activity's declaration in the `AndroidManifest.xml` file:

```xml
<activity
  
            android:label="@string/title_activity_deep_link"
  
            android:name="b3nac.injuredandroid.DeepLinkActivity">
  
            <intent-filter android:label="filter_view_flag11">
  
                <action android:name="android.intent.action.VIEW"/>
  
                <category android:name="android.intent.category.DEFAULT"/>
  
                <category android:name="android.intent.category.BROWSABLE"/>
  
                <data android:scheme="flag11"/>
  
            </intent-filter>
  
            <intent-filter android:label="filter_view_flag11">
  
                <action android:name="android.intent.action.VIEW"/>
  
                <category android:name="android.intent.category.DEFAULT"/>
  
                <category android:name="android.intent.category.BROWSABLE"/>
  
                <data android:scheme="https"/>
  
            </intent-filter>
  
        </activity>
```

We can see it can handle deep links using the "flag11://" schema.

Finally, inspecting the source code we can see that the real flag is being fetched from a Firebase storage and compared to the submitted flag.

We can bypass this step by searching for `https://injuredandroid.firebaseio.com/binary/.json`, as this is an unprotected endpoint, it will return the flag: `HIIMASTRING`.

Though, this is not the right way to do so, as all flags past the 8 flag do the same thing. The right way is to run the `assets/meŉu` binary, which will print the flag. How do I know this?

Because one of the hints tell you to do so. Yeah... this one wasn't that straight forward.

Eleventh flag:  `HIIMASTRING`




