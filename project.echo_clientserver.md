[< Index](./index.md)<br>

On 10th of October 2019,

I've built a simple echo server on sockets.
- Server listens
- Client connects and sends message
- Server reports the message and returns it
- Client reports the server's echo and stops

Compared what it took to write such program in pure C, rust is quite refreshing. It feels fresh like Python. At the same time the problems that plagued C are still there. If a socket breaks(client terminates) and we still read from it - the server returns the last read buffer with 0 bytes read as the result. Why is this a default behaviour? Why isn't it plugged automatically through some Err as result? Can sockets communicate in 0byte messages? Well atleast I knew exactly where the problem was. Always watch out for the number of bytes read!

The code is [here](https://github.com/simtron/rust_network/tree/master/simple_client_server) <br>
