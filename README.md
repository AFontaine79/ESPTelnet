ESPTelnet
=========

* Author: Lennart Hennigs (https://www.lennarthennigs.de)
* Copyright (C) 2018-2021 Lennart Hennigs.
* Released under the MIT license.

ESP8266/ESP32 library that allows you to setup a telnet server.


Description
-----------

Use this library to set up a the telnet server to communicate status messages or debug / error log output. This is especially useful when you don't have a serial connection to the ESP.

How To Use
----------

- You can use `print()` and `println()` to output text on the telnet server.

- The library uses callback handlers to notify you of the different telnet events such as connecting, reconnecting, ...

- You can use the `onInputReceived()` handler to receive text from the telnet server, as shown in the example

- A callback function needs a String parameter, where the IP from the connected client is sent (or the input text in case of `onInputReceived()`)


**Note:** For the class to work, you need to call the `loop()` member function in your sketch's `loop()` function. See the example for more details.

These are the constructors and the member functions the library provides:

```
    ESPTelnet();

    bool begin();
    void loop();
    void stop();

    void print(String str);
    void print(char c);
    void println(String str);
    void println(char c);
    void println();

    String getIP() const;
    String getLastAttemptIP() const;
    
    void onConnect(CallbackFunction f);
    void onConnectionAttempt(CallbackFunction f);
    void onReconnect(CallbackFunction f);
    void onDisconnect(CallbackFunction f);

    void onInputReceived(CallbackFunction f);
```



Installation
------------
Open the Arduino IDE choose "Sketch > Include Library" and search for "ESPTelnet". 
Or download the ZIP archive (https://github.com/lennarthennigs/ESPTelnet/zipball/master), and choose "Sketch > Include Library > Add .ZIP Library..." and select the downloaded file.


License
-------

MIT License

Copyright (c) 2018-2020 Lennart Hennigs

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
