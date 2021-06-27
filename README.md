# testWebServ

### I/ gcc server -> a.out
- **creates** a socket used only for accepting connections (blocking)
- **binds** an address struct to the socket
- tells the socket to **listen** and get prepared to accept int(backlog) connections
- --------loop--------
- **accepts** the first connection request in queue and creates a new socket for it (non-blocking), address struct receives client address
- 2-> **reads** client request in socket
- 3-> **writes** response into the socket fd
- **closes** socket, loop and returns
### II/ gcc client -> a.out
- **connects** to socket
- 1-> **sends** request to server through socket fd
- 4-> **reads** server response in socket
