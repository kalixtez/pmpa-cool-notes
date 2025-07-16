The first flag can be found in the application's source code, because the check is actually a hardcoded comparison between the entered value and the string literal.

```java
public final void submitFlag(View view) {
  
        EditText editText = (EditText) findViewById(R.id.editText2);
  
        d.s.d.g.d(editText, "editText2");
  
        if (d.s.d.g.a(editText.getText().toString(), "F1ag_0n3")) { // here!
  
            Intent intent = new Intent(this, (Class<?>) FlagOneSuccess.class);
  
            new FlagsOverview().J(true);
  
            new j().b(this, "flagOneButtonColor", true);
  
            startActivity(intent);
  
        }
  
    }
```

Flag: `F1ag_0n3`