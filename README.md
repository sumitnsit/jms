# JMS
### What is JMS?
JMS means Java Messaging Service.  It is a standard for inter client communication. It allows the J2EE application component to create, send, read and receive the messages.

### What type of messaging is provided by JMS?
JMS provides both type of messaging,

1. Synchronous: Synchronous messaging involves a client that waits for the server to respond to a message.
2. Asynchronous: Asynchronous messaging involves a client that does not wait for a message from the server. An event is used to trigger a message from a server.

### What do you mean by Synchronous and Asynchronous type of messaging?
**Synchronous:** In this type of messaging, client waits for the server to respond to a message.

**Asynchronous:** In this type of messaging, client does not wait for a message from the server, but automatically an event is created to trigger a message from a server. 

### How many types of messaging model do JMS provide for and what are they?
There are two types of messaging models that JMS provides –
1. Point to point queuing
2. Second one is public and subscribe

### Explain the difference between topic and queue?
Queue technique is used for one to one messaging, and it supports point to point messaging. While topic is typically used for one to many messaging and it supports public subscribe model of messaging.

### What is the role of the JMS provider?
The JMS provider handles data conversion, security of the messages and the client triggering.  It specifies the level of encryption, security level of the message and the best-data type for the non-JMS client.

### What are the components of JMS?

1. JMS provider
2. JMS client
3. Messages
4. Administered objects
5. Native clients

### For JMS-enabled application, what are the core JMS-related objects required?
The core JMS-related objects that are required are:

1. The connection object
2. One or more sessions within a connection that provides a context for message sending and receiving.
3. A topic or queue object within a session representing the destination within the message broker.
4. Appropriate sender or publisher or receiver within a session.

### What is JMS administered object?
JMS administered object is a pre-configured JMS object that is created by an administrator for the use of JMS clients and placed in JNDI namespace.

### What is JMS session?
A JMS session is a single-threaded context for sending and receiving JMS messages.  A JMS session could be a locally transacted, non-transacted or distributed transacted.

### Mention the difference between durable and non-durable subscription?
Durable subscription gives a subscriber the freedom of receiving all messages from a topic, while a non-durable subscription does not make any guarantees about messages sent by others when a client get disconnected by others.

### What is Byte Message?
Byte message is a stream of uninterrupted bytes. It contains an array of primitive bytes in its payload.  For the transfer of data between two applications in their native format, byte message is used, which may be not possible with other message types.
Mention different types of messages available in JMS API?

1. Stream Messages: Group of Java Primitives
2. Map Messages: Name Value Pairs. Name being a string& Value being a java primitive 
3. Text Messages: String messages (since being widely used a separate messaging Type has been supported) 
4. Object Messages: Group of serialize able java object 
5. Bytes Message: Stream of uninterrupted bytes

### What is a JMS client?
JMS client is a language program that sends or receives messages.

### What is the difference between JMS and RPC (Remote Procedure Call)?
The basic difference between JMS and RPC lies in the way they message. JMS uses asynchronous messaging type while, RPC creates synchronous messaging type. The method invoker in RPC, waits for the method to finish execution and return back the control to the invoker. In JMS the message sender just sends the message to the destination and continues its own processing.

### Message-driven beans?
Message-driven beans are a type of enterprise bean that enables the asynchronous consumption of messages.

### What is MOM in reference to JMS?
The MOM (Message Oriented Middleware) is a software that works as an intermediate between two communicating components.  It is placed between the client and server, MOM provides the facility of passing message by using the technique queuing. Until the client does not request to read the message, the messages will be stored in queue.  By using this technique, the software component can work independently of time.

### How you can deliver a java message to a non-java client?
It is according to the specification that the message sent should be received in the same format. A non-java client cannot receive a message in the form of java object. The provider in between handles the conversion of the data type and the message is transferred to the other end

### For sending messages through JMS, what encryption options are there?
The encryption and decryption of the messages is handled by JMS provider and not JMS specifications.

### What is the advantage of persistent message delivery compared to nonpersistent delivery?
If the JMS server experiences a failure, for example, a power outage, any message that it is holding in primary storage potentially could be lost. With persistent storage, the JMS server logs every message to secondary storage. The logged message is removed from secondary storage only after it has been successfully delivered to all consuming clients

### Why doesn't the JMS API provide end-to-end synchronous message delivery and notification of delivery?
JMS API messaging provides guaranteed delivery via the once-and-only-once delivery semantics of **PERSISTENT** messages. In addition, message consumers can ensure reliable processing of messages by using either **CLIENT_ACKNOWLEDGE** mode or **transacted sessions**. This achieves reliable delivery with minimum synchronization and is the enterprise messaging model most vendors and developers prefer. 

The JMS API does not define a schema of systems messages (such as delivery notifications). If an application requires acknowledgment of message receipt, it can define an application-level acknowledgment message.

### What is MDB and What is the special feature of that?
MDB is Message driven bean, which very much resembles the Stateless session bean. The incoming and out going messages can be handled by the Message driven bean. The ability to communicate asynchronously is the special feature about the Message driven bean.
 	
### What are the core JMS-related objects required for each JMS-enabled application?
Each JMS-enabled client must establish the following:

* A connection object provided by the JMS server (the message broker)
* Within a connection, one or more sessions, which provide a context for message sending and receiving
* Within a session, either a queue or topic object representing the destination (the message staging area) within the message broker
* Within a session, the appropriate sender or publisher or receiver or subscriber object (depending on whether the client is a message producer or consumer and uses a point-to-point or publish/subscribe strategy, respectively) 
* Within a session, a message object (to send or to receive)

### What are the advantages of JMS?
JMS is asynchronous in nature. Thus not all the pieces need to be up all the time for the application to function as a whole. Even if the receiver is down the MOM will store the messages on it's behalf and will send them once it comes back up. Thus at least a part of application can still function as there is no blocking.  

### Are you aware of any major JMS products available in the market?
IBM's MQ Series is one of the most popular product used as Message Oriented Middleware. Some of the other products are SonicMQ, iBus etc. All the J2EE compliant application servers come built with thier own implementation of JMS.

### What is the role of JMS in enterprise solution development?
JMS is typically used in the following scenarios

1. Enterprise Application Integration: Where a legacy application is integrated with a new application via messaging.
2. B2B or Business to Business: Businesses can interact with each other via messaging because JMS allows organizations to cooperate without tightly coupling their business systems.
3. Geographically dispersed units: JMS can ensure safe exchange of data amongst the geographically dispersed units of an organization.
4. One to many applications: The applications that need to push data in packet to huge number of clients in a one-to-many fashion are good candidates for the use JMS. Typical such applications are Auction Sites, Stock Quote Services etc.

### What is the use of Message object?
Message is a light weight message having only header and properties and no payload. Thus if receivers are to be notified about an event, and no data needs to be exchanged then using Message can be very efficient.

### What is the use of BytesMessage?
BytesMessage contains an array of primitive bytes in it's payload. Thus it can be used for transfer of data between two applications in their native format which may not be compatible with other Message types. It is also useful where JMS is used purely as a transport between two systems and the message payload is opaque to the JMS client. Whenever you store any primitive type, it is converted into it's byte representation and then stored in the payload. There is no boundary line between the different data types stored. Thus you can even read a long as short. This would result in erroneous data and hence it is advisable that the payload be read in the same order and using the same type in which it was created by the sender.

### What is the use of StreamMessage?
StreamMessage carries a stream of Java primitive types as it's payload. It contains some conveient methods for reading the data stored in the payload. However StreamMessage prevents reading a long value as short, something that is allowed in case of BytesMessage. This is so because the StreamMessage also writes the type information along with the value of the primitive type and enforces a set of strict conversion rules which actually prevents reading of one primitive type as another.

### What is the use of TextMessage?
TextMessage contains instance of java.lang.String as it's payload. Thus it is very useful for exchanging textual data. It can also be used for exchanging complex character data such as an XML document.

### What is the use of ObjectMessage?
ObjectMessage contains a Serializable java object as it's payload. Thus it allows exchange of Java objects between applications. This in itself mandates that both the applications be Java applications. The consumer of the message must typecast the object received to it's appropriate type. Thus the consumer should before hand know the actual type of the object sent by the sender. Wrong type casting would result in ClassCastException. Moreover the class definition of the object set in the payload should be available on both the machine, the sender as well as the consumer. If the class definition is not available in the consumer machine, an attempt to type cast would result in ClassNotFoundException. Some of the MOMs might support dynamic loading of the desired class over the network, but the JMS specification does not mandate this behavior and would be a value added service if provided by your vendor. And relying on any such vendor specific functionality would hamper the portability of your application. Most of the time the class need to be put in the classpath of both, the sender and the consumer, manually by the developer.

### What is the use of MapMessage?
A MapMessage carries name-value pair as it's payload. Thus it's payload is similar to the java.util.Properties object of Java. The values can be Java primitives or their wrappers.
