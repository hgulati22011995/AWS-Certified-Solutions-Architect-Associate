Nehra Classes — Session 2: Client-Server Architecture
Why Learn Client-Server Architecture?
Before diving into cloud computing (IaaS, PaaS, SaaS), it's essential to understand the fundamentals:
What is a client vs. a server?
How do they communicate?
What is a network, IP address, hostname resolution?
Types of client-server architecture
Stages an application goes through before reaching production
What is a Client? What is a Server?
Example: You open a browser on your personal computer and search something on google.com.
Your machine generates a packet/request → sent to Google's server asking for the search info
Google's server processes the request and sends back a response
This entire exchange happens within a fraction of a second
Role
Definition
Client
The machine that sends a request for a service
Server
The machine that listens to the request and sends back a response
Analogy: Patient (client) visits a doctor (server) for treatment.
Key Insight: Role, Not Structure
A machine is just a device until its role is defined:
If it accesses another machine's service → it acts as a client
If you install a package/service on it (e.g., SSH service) so other machines can connect to it → it acts as a server
The same physical machine can act as a client in one context and a server in another — even simultaneously. A device is called client or server based on its role at a given moment, not its structure.
Example: In a LAN you might have a PC, mobile phones, tablets, printers, a router — each could be a client or server depending on the role it's playing.
Network — The Medium of Communication
Just like a phone call needs a telephone line/mobile network, a client and server need a network to communicate.
Types of Networks
Network Type
Description
LAN (Local Area Network)
Client and server are on the same local network/router, communicating directly
Internet / Public Network
Used when client and server are on different networks — internet = interconnection of multiple networks
IP Address
IP = Internet Protocol Address
Every machine that is part of a network has a unique ID (analogous to an Aadhaar number identifying a person, their address, and details)
IP address lets you identify and communicate with a specific machine on a network
Types of Client-Server Architecture
Architecture "tiers" are decided based on the number of layers (client layer + server layer) involved.
1-Tier Architecture
2-Tier Architecture
3-Tier Architecture
N-Tier Architecture (more layers)
1-Tier Architecture
Example: Installing Apache on a computer and hosting a website — but the machine is not connected to any network (no LAN, no internet).
The website is only accessible locally, via the loopback address 127.0.0.1
Client and server exist on the same single machine
Only the same machine's users can log in and access it
Limitation: The service cannot be provided to any external user or another network — essentially no real-world use case for serving multiple clients.
2-Tier Architecture
Setup: A server (hardware: CPU, RAM, storage) with an OS installed (e.g., Linux), and both the application and database deployed together on the same machine, exposed to the public network via a public IP address.
This is essentially:
Hardware resources = Infrastructure (→ "Infrastructure as a Service" in cloud computing)
OS + Application + Database all running on one exposed server
Problems with 2-Tier Architecture:
Resource Contention
As the number of clients grows, both the application and database compete for the same CPU/RAM
Leads to performance issues, latency, machine hangs, unresponsive requests, or even downtime
Security Risk
Since the server is directly exposed to the public network, if a hacker compromises it, both the application and database are compromised together
If they were separated, only one component's data would be at risk
Leads to loss of client trust
Despite these limitations, many companies still use 2-tier architecture.
Application Development Stages (Before Production)
An application/software should never be deployed directly to a production environment. It passes through several stages first:
Development Environment
Application is designed and built here
Hosted on a Development Server
Developers check improvements, expected services, and functionality
Testing / QA Environment
Application moves to a Test Server
Testers verify if the application works as designed
If issues are found → sent back to development → fixed → retested
Also called Quality Assurance (QA) Environment
Production Environment
Once everything works as expected, the application is finally hosted on the Production Server
This is what actual end-users/clients interact with
Why This Matters for 2-Tier Architecture
In a 2-tier setup, you have:
1 Server layer (application + database together)
1 Client layer (users accessing it)
→ Hence called 2-Tier Architecture, though it has clear limitations (resource contention, security risk) which more advanced architectures (3-tier, N-tier) aim to solve.
Key Takeaways
Client/Server is a role, not a fixed machine type
A network (LAN or Internet/public network) is required for client-server communication
IP addresses uniquely identify machines on a network
Architecture tiers = number of client + server layers
1-Tier: client & server on same machine, local-only, no real-world use
2-Tier: app + database on one exposed server — simple but has performance and security risks
Applications must go through Development → Testing/QA → Production stages before serving real clients
