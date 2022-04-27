# OpenKYC
![image](https://user-images.githubusercontent.com/45710269/135753913-71af9e2d-3b6c-4a27-aaa9-b4c2b406f1a9.png) **OPen KYC**

[![Web Site](https://github.com/fastify/fastify/workflows/website/badge.svg)](https://github.com/fastify/fastify/actions/workflows/website.yml)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](https://standardjs.com/)

Open-Kyc comprises of two parts a REST layer and a r3Corda app
## Some Information on r3Corda
r3Corda is an open source blockchain platform we have used here. We do not own neither have developed r3Corda.   
<br> </br>   

* **Title:**
   Open-KYC provides a solution for redudant kyc requests, all you need to do is sign-up once on the platform and get verified by any one of the Banks and 
   then save yourself from filling those troublesome forms again, simply apply for KYC with click of a button.Open-Kyc is an Open-Source decentralized application running on r3Corda and a Nodejs server in the Back-end and Reactjs in the front-end, It can be easily integrated with your kyc portals too.

</br>

* **Pre-Requisites**
----
  `Node.js`
  `Express.js`
  `MongoDb`
  `JavaScript`
  `Reactjs`
  `r3Corda`

</br>

* **Implemenation of the REST API**

----
  `/user` 
  <p>
  Inserts the data provided by the user in the Data Base and takes care of login and signup activities.
  </p>

  `/kyc`
  <p>
  Provides the user with applying, checking status, getting details of their KYC's
  </p>
  
  `/utilroutes`
  <p>
  Provides the user with some additional functionalities of forgot-password, account-verification etc.
  </p>
 
  `/trackingroutes`
  <p>
  Provides the bank with the functionality of logging their transactions.
  </p>
 
 
----- 
* **Sample URL**

  /user/register:

* **Method:**

  `POST`
  
* **Data Params**

   **Required:**
 
   `Name=[String]`
   `email=[Email]`
   `aadharno=[integer]`
   `panno=[integer]`
   `usertype (Bank or Client)=[String]`
   `phone=[integer]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{sucess: "true", message: "Your Requested has been accepted" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{success: "false", message : "Could not process the request, Try again" }`

* **Handling a large number of Requests**
    * **Load Balancing**
        --> We will deploy the app on a kubernetes cluster and manage the load and traffic from there.
        
</br>

* **Setting Up**
----  
  
## Setup

- Install and setup [`Nodejs`](https://nodejs.org/en/)
- Install and setup [`Mongodb`](https://www.mongodb.com/)
- Install ans setup [`r3Corda`](https://www.r3.com/corda-platform/)
- Fork and Clone the repository

```sh
git clone https://github.com/LobRockyl/OpenKYC.git
```

- Start the r3Corda server and deploy the nodes
go into cordapp-example folder and run:

```sh
cd build/nodes
./gradlew deployNodes

```
Then in seperate windows:
replace X with A,B etc.
```sh
cd build/nodes/BankX  
java -jar corda.jar

```
If running 
Then seperately run their servers 

Running the server


- Move into the project folder

```sh
cd server
```

- Setup `.env` file

- Start the server

```sh
npm start server.js
```

The output should be

```sh
Server connected on Port 8000
```

Rnning the frontend:

Move into client, user folders and run

```sh
npm i
npm start
```
  
