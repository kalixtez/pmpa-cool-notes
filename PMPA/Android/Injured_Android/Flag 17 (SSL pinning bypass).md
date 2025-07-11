When the SSL pinning is bypassed (using the `android sslpinning disable` Objection command), we can use a proxy to intercept plaintext traffic. We can see the following:

```json
{"t":"d","d":{"b":{"p":"sslpinningbypass","d":"Epic_Awesomeness"},"a":"d"}}
```

That is an incoming Websocket reply, coming from the Firebase database. Testing the `d.b.d` field, we correctly guess that the seventeenth flag is: `Epic_Awesomeness`.