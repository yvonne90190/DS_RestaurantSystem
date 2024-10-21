# **Real Time Restaurant Ordering and Management System**

## **Overview**
This project is a full-fledged online ordering system that allows customers to place orders through a web interface, with real-time status updates from the kitchen. It uses **ETCD** as a distributed backend database for high availability and consistency, **React** for the frontend, and **Flask** for the backend.

### Key Features:
- **Order Creation**: Customers can create orders and track their status (Pending, Making, Finished).
- **Order Management**: The kitchen can accept, prepare, and complete orders, with status updates reflected back to the customer.
- **Distributed Backend**: Uses **ETCD** with the **Raft consensus algorithm** to ensure fault-tolerance and high availability.
- **Real-Time Communication**: Backend services communicate with the frontend via RESTful APIs to reflect the current status of orders.

---

## **System Architecture**
This project is designed as a microservice-based distributed system. It includes:

- **Frontend**: A responsive React web application where customers place and track orders.
- **Backend**: A Flask server managing order processing, communicating with ETCD for database operations.
- **ETCD**: A distributed key-value store, used to store orders, handle consensus, and ensure data consistency.
- **Raft Consensus**: Ensures strong consistency across the distributed database by managing leader elections and log replication.

For a detailed look at the system's internal workings, refer to the **Activity Diagram** and **Sequence Diagram** below:

- **Activity Diagram**: Represents the flow of order creation, acceptance, cancellation, and completion.  
  ![image](https://github.com/yvonne90190/Real-Time-Restaurant-Ordering-and-Management-System/assets/74034659/d0411f0d-d440-413a-a96f-784f42d74ed2)


- **Sequence Diagram**: Illustrates the interactions between the user, ETCD server, Raft module, and leader node during the ordering process.  
![image](https://github.com/HOSHICHEN7267/DS_RestaurantSystem/blob/master/image/Sequence%20Diagram.png)

- [Demo video](https://youtu.be/513C4WNDiVs)
- [Presentation PowerPoint](https://github.com/HOSHICHEN7267/DS_RestaurantSystem/blob/master/Introduction%20of%20Restaurant%20System.pdf)


---

## **Getting Started**

### **Prerequisites**
To run this project, you'll need to have the following installed on your system:
- **Python 3.x**
- **Flask**
- **React.js**
- **ETCD**
- **Docker** (optional for running ETCD in a container)

---

## **Database (ETCD) Design**

- Orders are stored in ETCD using a **key-value** format. The key represents the order ID, and the value contains the order details (e.g., items, customer information, status).
  
- **Raft Consensus** ensures consistency across multiple ETCD nodes. This guarantees that all nodes have the same order information, even if some nodes fail.

---

## **Acknowledgments**
- Thanks to the creators of **ETCD**, **Flask**, and **React** for providing the tools and libraries used in this project.
- Special thanks to the Raft consensus algorithm for making distributed systems fault-tolerant.
