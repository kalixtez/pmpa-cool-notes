For flag number 4, the comparison is done as follows:

```java
String string = editText.getText().toString();
  
        byte[] bArrA = new g().a();
  
        d.s.d.g.d(bArrA, "decoder.getData()");
  
        if (d.s.d.g.a(string, new String(bArrA, d.w.c.f2418a))) {
```

Further inspecting the source code, the `g` class is defined as follows:

```java
public class g {
  
  
    /* renamed from: a, reason: collision with root package name */
  
    private byte[] f1468a = Base64.decode("NF9vdmVyZG9uZV9vbWVsZXRz", 0);
  
  
    public byte[] a() {
  
        return this.f1468a;
  
    }
  
}
```

Base64-decoding the `NF9vdmVyZG9uZV9vbWVsZXRz` strings yields the the flag.

Fourth flag: `4_overdone_omelets`