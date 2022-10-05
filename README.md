# Protocol design
The first goal is to **specify a client-server protocol**, which will **allow a client to ask a server to compute a calculation and to return the result**. 

You decide the functionality to be implemented, but KEEP IT SIMPLE. Essentially, as a client I should be able to send an operation (addition or multiplication) to the server and get my result back. Of course, once you have the basics in place, you can extend as much as you want. But we do not expect a fully functional calculator, with 1'000 operations and features.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d1/Calculator_on_macOS.png/381px-Calculator_on_macOS.png)

The specification must contain <u>**everything**</u> that is needed for **one person to implement a client**, for **another person to implement a server** and for the 2 applications to work together. The specification is a **contract** between the server and the client.

## Phase 1: write the specification (individually, 20 minutes)

Fork this repo and **create a folder with your GitHub ID in the "specs" folder** (like you did for the Chill lab at the beginning of the semester).
Then, in this folder, create a file named `protocol.md` and write your **specification**:
* Protocol objectives: what does the protocol do?
* Overall behavior:
  * What transport protocol do we use?
  * How does the client find the server (addresses and ports)?
  * Who speaks first?
  * Who closes the connection and when?
* Messages:
  * What is the syntax of the messages?
  * What is the sequence of messages exchanged by the client and the server? (flow)
  * What happens when a message is received from the other party? (semantics)
* Specific elements (if useful)
  * Supported operations
  * Error handling
  * Extensibility
* Examples: examples of some typical dialogs.
  
## Phase 2: review 3 specifications (in pairs, 5 minutes)

- Are there big differences between the specification?
- What are the common elements?
- Are there missing or confusing elements in the specification?

## Phase 3: validate specs in pairs (in pairs, 20 minutes)

* Work with the student sitting next to you
* One of them is the server, the other is the client
* Pick one of the 2 specifications
* One student uses netcat (nc) to start a server (nc -kl). The other student uses netcat to start a client.
* Go through a couple of scenarios to validate that your specification is complete (**if you need to ask something to the other student, or if you need to discuss, you probably should make your specification more complete**)

After writing and validating the specification, **submit a Pull Request**

## Phase 4: watch our proposal (individually, 15 minutes)

* https://www.youtube.com/watch?v=95GwsyiSMXI&list=PLfKkysTy70QaSEH6AqwIzVqHJKId73sqR&index=5&t=5s

## Phase 5: compare our proposal with your solution (20 minutes)

## Phase 6: execute and read the samples TCP projects (60 minutes)

Read and run the examples 04-StreamingTimeServer and 05-DumbHttpClient as examples how to implement a TCP server and a TCP client.

## Phase 7: implement a client and a server (180 minutes)

- Use the skeleton provided as a basis
- One student implements a client in Java
- The other student implements a server in Java. The server can be single threaded (doesn't use threads) or multithreaded. The single-threaded server is slightly easier to implement. **However, in a test you should be able to implement the multi-threaded version**.
- The team performs various tests to validate that the client and the server work together (on the same machine, across two machines connected to the same network, ...)
- Add your code in your folder and submit a PR on the upstream server.
