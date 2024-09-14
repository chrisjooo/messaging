# Websocket exploratory
Here I learn about what is websocket and how to use it in golang, i will create a simple web-based messaging app. 

## Websocket
WebSocket is a protocol that provides full-duplex communication channels over a single TCP connection. It is built on top of HTTP and begins with an HTTP handshake to establish the connection. Once the WebSocket connection is established, it upgrades from HTTP to WebSocket and continues communication over TCP - ChatGPT

```mermaid
sequenceDiagram
Client(javascript)->>Server(Golang): Connect
Server(Golang)->>Server(Golang): Append connection to connection pools
loop CheckRequest
    Server(Golang)->>Server(Golang): Check each connection gives payload
    Client(javascript)->>Server(Golang): Gives Message "Hello"
    loop For-each-connection-in-pools
        Server(Golang)->>Client(javascript): Gives Message "Hello"
    end
    Client(javascript)->>Server(Golang): Terminate connection
    Server(Golang)->>Server(Golang): Remove connection from pools
end
```

simple web chat and source code reference: https://dasarpemrogramangolang.novalagung.com/D-golang-web-socket-chatting-app.html
