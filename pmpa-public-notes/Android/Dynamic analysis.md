When the application is running, the outgoing traffic might be inspected using proxy tools such as Proxyman and Burp Suite. If SSL pinning is active, it must first be bypassed. This can be done with [[Objection]]. Once that's out of the way, just redirect the phone's traffic to the tool and the plaintext traffic will be readable.

## The /data/data directory

Inside the `/data/data/<package_name>` directory, the app will store files created during runtime. The nature of said files will vary, but we are interested in most of them, and it's worth taking a look at them. SQLite databases and `.json` files are of special attention. The latter kind potentially contains runtime configuration parameters/cached credentials and more.