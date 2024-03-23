# ADVPROG Module 6

## Commit 1 Reflection
This Rust code is a simple TCP server that listens for incoming connections on port 7878.

The use statement at the top of the file imports the necessary modules from the Rust standard library. TcpListener and TcpStream are used for networking, while BufReader and prelude::* are used for reading from the network stream.

The main function is the entry point of the program. It creates a new TCP listener that binds to the local address 127.0.0.1 (localhost) on port 7878. The unwrap() function is used to handle any potential errors that might occur when creating the listener.

The main function then enters a loop that waits for incoming connections to the listener. When a connection is made, it is passed to the handle_connection function.

The handle_connection function takes a mutable TCP stream as an argument. It creates a new buffered reader that wraps the TCP stream, which allows the program to read from the stream line by line.

The function then reads lines from the buffered reader, unwraps the results, stops reading when it encounters an empty line, and collects the lines into a vector. This vector represents the HTTP request that was read from the stream.

Finally, the handle_connection function prints the HTTP request to the console.

The bind, incoming, unwrap, lines, and is_empty functions are part of the Rust standard library and are used to implement the functionality described above.


## Commit 2 Reflection
![Commit 2 screen capture](/assets/images/commit2.png)

The code snippet processes incoming data from a TCP stream. It reads lines from the stream, collects them into a vector, and then constructs an HTTP response. This response includes a status line, the length of the file content, and the file content itself. Finally, it sends the response back to the client via the stream.

Key steps:

1. Use BufReader to read incoming data line by line.
Take lines as long as they are not empty and collect them into a vector of strings.
2. Read the contents of the file "hello.html" into a string.
3. Calculate the length of the file contents.
4. Format an HTTP response containing the status line, content length, and file contents.
5. Send the response back to the client via the TCP stream.
6. The code may panic if there's an error while reading or sending data, as it uses unwrap() extensively without error handling.


## Commit 3 Reflection
![Commit 3 screen capture](/assets/images/commit3.png)
The code snippet reads the request from the client, if the request_line is a GET request to the / path, it sends the contents of the hello.html file as a response. If the request is not a GET request to the / path, it sends a 404 Not Found response. The refactoring at the end of the steps is to reduce repeated code

## Commit 4 Reflection
If the user request line is `GET /sleep HTTP/1.1`, then the thread is being put to sleep for 10 seconds, that's why it is slow to load it.


## Commit 5 Reflection
Managing tasks concurrently in Rust often involves utilizing a thread pool, which comprises pre-allocated worker threads. These pools efficiently handle asynchronous tasks, ranging from parallelizing CPU-bound workloads to executing non-blocking I/O operations, thus alleviating the burden on the main thread.
