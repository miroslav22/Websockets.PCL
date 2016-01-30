## WebSocket.Portable

WebSocket.Portable is a PCL Profile 259 C# implementation of the [WebSocket protocol](https://tools.ietf.org/html/rfc6455). This plugin uses .net 4.5 and is compatible Xamarin Android, and Xamarin iOS.

This project is a binding library that makes use of native (Java / Objective-C) websockets to get around the limitations and jank of mono based websockets.

### NuGet
https://www.nuget.org/packages/WebSocket.PCL/

### Usage

`````
        void Connect()
        {
            connection = Websockets.WebSocketFactory.Create();
            connection.OnOpened += Connection_OnOpened;
            connection.OnMessage += Connection_OnMessage;
        }

        void Send()
        {            
            connection.Open("http://echo.websocket.org");
            connection.Send("Hello World");
        }

        private void Connection_OnOpened()
        {
            Debug.WriteLine("Opened !");
        }

        private void Connection_OnMessage(string obj)
        {
            Echo = obj == "Hello World";
        }
`````

### Example

There is a XamarinApp.Droid example in the /Examples/ folder.

### TODO

- Support other platforms. Will implement as requested.


### Questions

Post onto the Github [issue system](https://github.com/NVentimiglia/WebSocket.PCL) or contact me via my [website](http://avariceonline.com)