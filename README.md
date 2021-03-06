# rent-a-car-spring-react

#### Technologies 
<hr/>

    OpenJdk 11
    Apache Maven 3.6.3 
    Spring boot 2.4.0 M2
    Mongo DB  
    Docker Engine Community 19.03.12
    
A web application system to be used by the company staff, which could help them manage the rent a car business. This system helps business employees manage customer and car records.

#### Objectives
<hr/>
The core objectives are:
<ol>
    <li>Company Staff should be able to register <b>Customers</b> and <b>Cars</b> to be rented with required details</li>
    <li>Company Staff should be able to calculate total charges and release the car for rent upon completion of payment</li>
    <li>Company Staff should be able to generate Weekly/Monthly sales report</li>
    <li>Create Update Retrieve Delete Operations on Cars and Customers Data</li>
    <li>The System will ask the User to enter the necessary details for the customers and for the cars with the rental cost per day</li>
    <li>Unique GUI for the interactions of Users with the System </li>
    <li>The System must allow the customers to perform a car rental transaction </li>
</ol>

#### Setting Up Mongo DB
<hr>

The systems data will be stores in a mongo database. The database consists of the following collections.

    Customers Collections
    Cars Collections
    Sales Collections
    Employees Collections

The system admin user can be created by executing a bash inside mongo db container by 

    docker container exec -it containername sh
    //type the following in mongo
    mongo 
    show dbs // list all databases
    show collections // list all collections
    create database dbname // replace db name with a name of your choice
    //create an Admin User for Mongo DB
    > db.createUser({ user: "SYS_ADMIN", pwd:"ADMIN1234", roles:[{role:"userAdmin", db:"dbname"}] })

Once the user is created, use any IDE to go inside the monogo db and to manage the database
you will require to enter

    ip: localhost
    port: 27017
    username: user you just created
    password: password you just assigned
    database: database name you have given
    
#### Spring Boot JAVA CRUD Restful API Endpoints

The system must be able to call a list of cars and customers from the database

In order to envoke an endpoint the following schema is to be followed


##### GET API FOR THE COLLECTIONS MENTIONED ABOVE

    http://localhost:8085/car/get/all
    http://localhost:8085/car/get/{id}    
    http://localhost:8085/customer/get/all
    http://localhost:8085/customer/get/{id}    
    http://localhost:8085/employee/get/all
    http://localhost:8085/employee/get/{id}    
    http://localhost:8085/sales/get/all
    http://localhost:8085/sales/get/{id}    
    http://localhost:8085/order/get/all
    http://localhost:8085/order/get/{id}    
                    
##### POST API FOR THE COLLECTIONS MENTIONED ABOVE

    http://localhost:8085/car/create    
    http://localhost:8085/customer/create    
    http://localhost:8085/employee/create   
    http://localhost:8085/sales/get/create   
    http://localhost:8085/order/create
 
 The model details are to be posted in Request Body as application/json


##### PUT API FOR THE COLLECTIONS MENTIONED ABOVE

    http://localhost:8085/car/update    
    http://localhost:8085/customer/update    
    http://localhost:8085/employee/update   
    http://localhost:8085/sales/get/update   
    http://localhost:8085/order/update
 
 The model details are to be posted in Request Body as application/json, 
 moreover the id must be included in the Request Body to send a PUT Request.
  
##### DELETE API FOR THE COLLECTIONS MENTIONED ABOVE

    http://localhost:8085/car/delete/{id}    
    http://localhost:8085/customer/delete/{id}    
    http://localhost:8085/employee/delete/{id}   
    http://localhost:8085/sales/get/delete/{id}   
    http://localhost:8085/order/delete/{id}
 
 The model details are to be posted in Request Body as application/json, 
 moreover the id must be included in the Path variable to send a delete Request.
 
 
 
 
         
        
                    
    