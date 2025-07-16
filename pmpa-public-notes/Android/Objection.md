To patch a pulled apk using Objection, the `objection [-V optional_version] patchapk --source /path/to/apk` is used. After that, simply drag the apk to the emulator and the installation will automatically begin. Note: this process might sometimes fail, in which case manual patching, signing and realigning must be done.

To connect to the Frida server that the patched application will launch, simply run `objection explore`.

On a different notice, I had to install Objection like this:

`pip install objection`
`pip uninstall frida`
`pip uninstall frida-tools`
`pip install frida==16.7.19`

To get it to work. Otherwise, it seems like changes were introduced in Frida `17.0.0 >` that break Objection's connection to the server, leading to a `ObjC not defined` error, crashing the process and not allowing me to connect to the gadget.

If this method is used, type `-V 16.7.19` as an option to the patchapk command, just to make sure. (I didn't try without it, but I guess it isn't necessary, if installed as previously explained).

## SSL pinning bypassing

To bypass SSL pinning, Objection communicates with the frida-server process embedded in the application. The `android sslpinning disable` command in Objection's REPL will attempt to disable the pinning. Once disabled, traffic can be normally captured and forwarded using a proxy like Burpsuite.