# Middleware Engineering "DEZSYS_GK_HELLOWORLD_GRPC"

## Aufgabenstellung
**Group size:** 1 Person

### Requirements – Basics (Grundlagen)

- Answer the questions below about the **gRPC framework**.
- Use one of the tutorials listed under **"Links & Further Resources"** to create a simple **HelloWorld** application using the gRPC framework.
- **Create the Proto file** where you define your gRPC service and its data structures.
- **Implement a gRPC server and client** in a programming language of your choice.
- **Document each development step** in your protocol:
    - Describe the most important code snippets in a few sentences.
    - Document the **application output**.
    - Record any **problems or errors** encountered during development.

---

### Requirements – Extended Basics (Erweiterte Grundlagen)

- Customize the service so that a simple **DataWarehouse record** (see exercise MidEng 7.1) can be transferred.
- Document **which parts of the program need to be adapted** to support this.

---

### Requirements – Advanced (Vertiefung)

- Develop the **DataWarehouse client in another programming language**.
- Document the development of the **new DataWarehouse client**.
## Fragen

### **What is gRPC and why does it work across languages and platforms?**
gRPC is a high-performance remote procedure call framework using HTTP/2 and Protocol Buffers.  
It works across languages/platforms because auto-generated code is available for many languages based on the same `.proto` file.

---

### **Describe the RPC life cycle starting with the RPC client.**
Client calls stub → stub serializes request → request sent to server → server deserializes and executes → server returns response → client receives and deserializes response.

---

### **Describe the workflow of Protocol Buffers?**
Define messages in `.proto` file → run protoc compiler → generated code is created → application uses generated code to serialize/deserialize data.

---

### **What are the benefits of using Protocol Buffers?**
- Very fast
- Compact binary format
- Strong typing
- Backward/forward compatibility
- Auto-generated code

---

### **When is the use of Protocol Buffers not recommended?**
- When human-readable data is needed
- For very simple systems where JSON is enough
- In browser-only scenarios without gRPC-Web

---

### **List 3 different data types that can be used with Protocol Buffers.**
- `string`
- `int32`
- `bool`

## Implementierung

Start HelloWorldServer (Java)  
`gradle clean build`  
`gradle runServer`

Start HelloWorldClient (Java)  
`gradle runClient`
  

-------------------------------- Python 

Add grpcio packages  
`pip3 install grpcio grpcio-tools`  

Compile .proto file  
`python3 -m grpc_tools.protoc -I src/main/proto  
  --python_out=src/main/resources  
  --grpc_python_out=src/main/resources  
  src/main/proto/hello.proto`  

Start HelloWorldClient (Python)  
`python3 src/main/resources/helloWorldClient.py`  

## Quellen

- https://grpc.io/
- https://grpc.io/docs/languages/java/quickstart/
- https://yidongnan.github.io/grpc-spring-boot-starter/en/
- https://blog.shiftasia.com/introduction-grpc-and-implement-with-spring-boot/
- https://www.baeldung.com/grpc-introduction
- https://intuting.medium.com/implement-grpc-service-using-java-gradle-7a54258b60b8
- HelloWorld Source Files: https://elearning.tgm.ac.at/mod/resource/view.php?id=188440
- Intro Video (5min): https://grpc.io/docs/what-is-grpc/introduction
- Intro Video (15min): https://grpc.io/docs/what-is-grpc