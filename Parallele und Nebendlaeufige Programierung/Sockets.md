Ein Socket ist ein Endpunkt, der fuer das Senden und Empfangen von Nachrichten zustaendig ist, ein Socket wird identifiziert durch:
- Protokoll(UDP, TCP)
- IP Adresse
- Port

## Berkley Socket API
1. Socket - Create a new communication endpoint
2. Bind - Assign a local Address to the socket
3. Listen - Wait for another Process to contact us
4. Accept -  Passively accept an incoming connection request
5. Connect - Connect to a process that is listening
6. Send - send data
7. Receive - Receive data
8. Close - release the binding
