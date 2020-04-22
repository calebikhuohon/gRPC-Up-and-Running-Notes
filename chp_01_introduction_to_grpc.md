## Introduction to gRPC

A modern software system is a collection of distributed software 
applications that are running at different network locations and communicate with each other with message passing using 
different communication protocols.

With the advent of microservices architecture and cloud native architecture, conventional software applications that are
built for multiple business capabilities are further segregated into a collection of fine-grained, autonomous, and 
business capability-oriented entities which require connections to a network via inter-process (or inter-service or 
inter-application) communication techniques. 

Inter-process communication techniques are one of the most important aspects of modern distributed software applications.
They are usually implemented using message passing with synchronous request-response style or asynchronous event-driven 
styles.

For most use cases, RESTful services are quite bulky, inefficient, and error-prone for building inter-process 
communication. In contrast, gRPC solves the issues associated with using REST for synchronous request-response style 
communication among services and can also operate in fully asynchronous or streaming mode once the initial communication
is established. 

### What is gRPC?
gRPC (the "g" stands for something different in every gRPC release) is an inter-process communication technology that
allows you to connect, invoke, operate, and debug distributed heterogenous applications as easily as making a local 
function call. 

The following steps are involved in developing a gRPC application:
* **defining a service interface**: This contains information on how your service can be consumed by consumers, what methods 
  you allow the consumers to call remotely, what method parameters and message formats to use when invoking those methods, 
  and so on. The language used to specify a service definition is known as an **interface definition language (IDL)**. gRPC 
  uses protocol buffers as the IDL to define the service interface. Protocol buffers are a language-agnostic, 
  platform-neutral, extensible mechanism to serializing structured data.
  
* **generate the server-side and client-side code using the service definition**: This provides low-level 
communication abstractions. The generated file contains methods which hide low-level communication for different 
programming languages. These methods can be remotely invoked as easily as making a local function invocation. With the gRPC
plugin for protocol buffers, you can generate gRPC server-side and client-side code.
On the server side, you:
 * Implement the server logic of the generated service skeleton by overriding the base service class.
 * Run a gRPC server to listen for requests from clients and return the service responses.

On the client-side, you:
 * Invoke methods from the generated stub file which then translates to remote function invocatioin network calls to the
  server side.
  
### Client-Server Message Flow

When a gRPC client invokes a gRPC service, the client-side gRPC library uses protocol buffers and marshals the RPC call 
protocol buffer format, which is sent over HTTP/2. This request is unmarshaled on teh server side and the respective 
procedure invocation is executed using protocol buffers. The response follows a similar execution flow from the server 
to the client. 

### Advantages of gRPC
* It is efficient for inter-process communication
* It has simple, well-defined service interfaces and schema
* It's strongly typed
* It's polyglot  
* It has duplex streaming
* It has built-in commodity features
* It's integrated with cloud native ecosystems
* It's mature and has been widely adopted

### Disadvantages of gRPC
* It may not be suitable for external-facing services
* Drastic service definition changes are a complicated development process
* The ecosystem is relatively small

### gRPC vs Apache Thrift 
 **Transport**: gRPC is more opinionated and offers first-class support for HTTP/2.
 
 **Streaming**: gRPC service definitions natively supports bidirectional streaming.
 
 **Adoption and community**: gRPC has a good ecosystem around Cloud Native Computing Foundation (CNCF) projects
 
 **Performance**: No official results comparing both technologies.
 
### gRPC vs GraphQL
* GraphQL is more suitable for external-facing services or APIs that are exposed to consumers directly.
  
  
    
 

  
