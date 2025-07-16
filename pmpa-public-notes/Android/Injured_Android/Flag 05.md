Analyzing the source code of the `FlagFiveReceiver` class, we can see that it will reveal the flag after the `i2` variable is > 2, which happens after you visit the button three times.
```java
 // android.content.BroadcastReceiver
// [...]  
    public void onReceive(Context context, Intent intent) {
  
        String string;
  
        int i;
  
        d.s.d.g.e(context, "context");
  
        d.s.d.g.e(intent, "intent");
  
        j.j.a(context);
  
        int i2 = f1454a;
  
        if (i2 != 0) {
  
            string = "Keep trying!";
  
            if (i2 != 1) {
  
                if (i2 != 2) {
  
                    Toast.makeText(context, "Keep trying!", 1).show();
  
                    return;
  
                }
  
                String str = "You are a winner " + k.a("Zkdlt0WwtLQ="); // here!
  
                new FlagsOverview().H(true);
  
                new j().b(context, "flagFiveButtonColor", true);
  
                Toast.makeText(context, str, 1).show();
  
                i = 0;
  
            }
  
            f1454a = i;
  
        }
  
        StringBuilder sb = new StringBuilder();
  
        sb.append(d.w.h.e("\n    Action: " + intent.getAction() + "\n\n    "));
  
        sb.append(d.w.h.e("\n    URI: " + intent.toUri(1) + "\n\n    "));
  
        string = sb.toString();
  
        d.s.d.g.d(string, "sb.toString()");
  
        Log.d("DUDE!:", string);
  
        Toast.makeText(context, string, 1).show();
  
        i = f1454a + 1;
  
        f1454a = i;
  
    }
```

The flag is base64 encoded. The code that sends the message to the receiver is the following (in `FlagFiveActivity`):

```java
button.setOnClickListener(new View.OnClickListener() { // from class: b3nac.injuredandroid.b
  
            @Override // android.view.View.OnClickListener
  
            public final void onClick(View view) {
  
                this.f.H(view);
  
            }
  
        });

// this.f.H() definition:

public /* synthetic */ void H(View view) {
  
        F();
  
    }

// F() definition:

 public void F() {
  
        sendBroadcast(new Intent("com.b3nac.injuredandroid.intent.action.CUSTOM_INTENT"));
  
    }
```

It can also be done using the `am` after obtaining and `adb` shell:

`am broadcast -a b3nac.injuredandroid.intent.action.CUSTOM_INTENT -n b3nac.injuredandroid/.FlagFiveReceiver ` to send the message to the receiver.

Fifth flag: `{F1v3!}`