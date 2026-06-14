Terminal 1 (Server)
python server.py

Expected Output:

[SERVER] Listening on 127.0.0.1:5000
[SERVER] Waiting for client connection...
Terminal 2 (Client)
python client.py

Expected Output:

[CLIENT] Attempting to connect...
[CLIENT] Connected to server at 127.0.0.1:5000
Test Case 1: Successful Connection and Message Exchange
Client
Enter message (type 'quit' to exit): Hello Server
[SERVER]: Server received: Hello Server
Server
[SERVER] Connected to client: ('127.0.0.1', 54321)
[CLIENT]: Hello Server
Test Case 2: Server Receiving Messages
Client
Enter message (type 'quit' to exit): Testing Socket Connection
Server
[CLIENT]: Testing Socket Connection
Test Case 3: Client Receiving Responses
Client
[SERVER]: Server received: Testing Socket Connection
Test Case 4: Error Handling When Server Is Not Running
Close the server.
Run the client.
Client Output
[CLIENT] Attempting to connect...
[ERROR] Connection refused. Server is not running.
[CLIENT] Closing socket.

This demonstrates proper exception handling using:

except ConnectionRefusedError:
Test Case 5: Clean Disconnection
Client
Enter message (type 'quit' to exit): quit
[CLIENT] Disconnecting from server...
[CLIENT] Closing socket.
Server
[CLIENT]: quit
[SERVER] Shutdown requested by client.
[SERVER] Closing server socket.
