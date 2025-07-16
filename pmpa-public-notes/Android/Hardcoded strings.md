What to look for?
* Hardcoded API keys
* Hardcoded credentials (for bypassing)
* Hardcoded URLs
* Hardcoded firebase.io URLs
* Hardcoded bucket endpoints

We can do this using JDAX-GUI, and looking for the `.xml` files in the `res/values` directory. We can also inspect the source code using the `Text search` tool that JADX provides.

Common strings to search for are:
* "API"
* "Firebase"
* "Password"
* "SQL"
* "http://"
* "https://"