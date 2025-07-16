From the `FlagSevenSqliteActivity` class source code we can see the following:
```java
//[...]
    public void onCreate(Bundle bundle) {
  
        super.onCreate(bundle);
  
        setContentView(R.layout.activity_flag_seven_sqlite);
  
        C((Toolbar) findViewById(R.id.toolbar));
  
        j.j.a(this);
  
        H();
  
        ((FloatingActionButton) findViewById(R.id.fab)).setOnClickListener(new a());
  
        SQLiteDatabase writableDatabase = this.x.getWritableDatabase();
  
        ContentValues contentValues = new ContentValues();
  
        contentValues.put("title", Base64.decode("VGhlIGZsYWcgaGFzaCE=", 0));
  
        contentValues.put("subtitle", Base64.decode("MmFiOTYzOTBjN2RiZTM0MzlkZTc0ZDBjOWIwYjE3Njc=", 0));
  
        writableDatabase.insert("Thisisatest", null, contentValues);
  
        contentValues.put("title", Base64.decode("VGhlIGZsYWcgaXMgYWxzbyBhIHBhc3N3b3JkIQ==", 0));
  
        contentValues.put("subtitle", h.c());
  
        writableDatabase.insert("Thisisatest", null, contentValues);
  
    }
// [...]
```

An SQLite database is being accessed, and this database is destroyed when the activity finished (handled on the `onDestroy` function). In the time the activity is running the, a database named `Thisisatest.db` will exist too, and the instructions in the code above will insert those B64 encoded values in the `title` and `subtitle` columns of the `Thisisatest` table. Analyzing those values, we can see that `MmFiOTYzOTBjN2RiZTM0MzlkZTc0ZDBjOWIwYjE3Njc=` is decoded to:

`2ab96390c7dbe3439de74d0c9b0b1767`

This is a hash, and with a simple Google search (no need to crack it using tools) we realize that this is the MD5 digest of the `hunter2` string. Which is the first flag for the challenge.

The decoding of the second string though, `VGhlIGZsYWcgaXMgYWxzbyBhIHBhc3N3b3JkIQ==` yields what seems to be nonsense:

`9EEADi^^:?;FC652?5C@:5]7:C632D6:@]4@>^DB=:E6];D@?` but what is this exactly? It might seem non sensical at first, but it could be an encoded string. Testing a few different encoding algorithms on Cyberchef, one will eventually reach ROT47. Performing a ROT47 deciphering to this string yields an URL: `https://injuredandroid.firebaseio.com/sqlite.json`.

Upon visiting the URL, a single json reply will be given back to the requester:

`S3V3N_11`

Finally, the two strings that solve the challenge:

flags-07 = {`hunter2`, `S3V3N_11` }