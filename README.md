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
