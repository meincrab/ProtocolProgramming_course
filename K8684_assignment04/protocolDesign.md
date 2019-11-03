# K8684 Alexander Andreev
# SIMPLE FILE TRANSFER PROTOCOL DESIGN DOCUMENT
## Description : 

This is a design document for simple file transfer protocol.  
Protocol MUST have two possible requsets LIST and DOWNLOAD and also two possible responses ERROR and FILE. Protocol MUST use sockets and SHOULD use TCP(Transmission Control Protocol) for connection and data transfering between CLIENT and SERVER. TCP is needed for making sure about integrity of sent and received data.  Client is sending requests to the server, server is answering to requests with response. Protocol is stateless and doesn't have authentication like username and password.  

  
## Requests and Responses
Requests and Responces are formatted in plain text. Each request and responce consists of two parts, HEADER-part and BODY-part. HEADER MAY contain information about FILENAME and MUST contain infromation about message length. Body MUST contain PAYLOAD such as DATA or Error Message.

## Requests  
### LIST - Request  
LIST  lists the filenames of the files available on the server.

#### Example Request
LIST {address} {port}  
LIST localhost 8888  
### Example Response  
Files:  
cat.jpg  
dog.jpg  
parrot.jpg  
  
### DOWNLOAD - Request  
DOWNLOAD downloads a file. A filename has to be provided.  
  
#### Example Request 
DOWNLOAD localhost 8888 test.jpg


## Responces  

### ERROR - Responce  
ERROR tells the client that the request could not be processed. The error message can be describe several different kinds of errors.  
  
#### Example Request 

#### Example Responce  

### FILE - Responce  
FILE returns the data to the client.  
  
#### Example Request  
#### Example Responce  

### Reference material:  
HTTP Protocol  
https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html  
RFC2119  
https://tools.ietf.org/html/rfc2119  
TCP  
https://tools.ietf.org/html/rfc793