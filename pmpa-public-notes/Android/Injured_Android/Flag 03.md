Flag 3 can be found in the resource files. On the source code, the following comparison is performed:

```java
    public final void submitFlag(View view) {
  
        EditText editText = (EditText) findViewById(R.id.editText2);
  
        d.s.d.g.d(editText, "editText2");
  
        if (d.s.d.g.a(editText.getText().toString(), getString(R.string.cmVzb3VyY2VzX3lv))) {
  
            Intent intent = new Intent(this, (Class<?>) FlagOneSuccess.class);
  
            new FlagsOverview().L(true);
  
            new j().b(this, "flagThreeButtonColor", true);
  
            startActivity(intent);
  
        }
  
    }
```

We can see that the comparison draws its right hand side from `R.string.cmVzb3VyY2VzX3lv`, which is a resource string. Resource strings are declared in the `strings.xml` resource file at build time by the developer and accessed by using:

`R.<resource_type>.<resource_name>`

Looking up the string with id `cmVzb3VyY2VzX3lv` in the source files, we can find the following:

```xml
<!-- On the resources.arsc file -->
<public type="string" name="cmVzb3VyY2VzX3lv" id="0x7f0f002f" />
```

```xml
<!-- On the /res/values/strings.xml file -->
<string name="cmVzb3VyY2VzX3lv">F1ag_thr33</string>
```

Third flag: `F1ag_thr33`