# 🏢 School Management System

## 📚 Overview  
The **School Management System** is a Spring Boot application that provides RESTful APIs to manage **schools and students** using **MongoDB**, which runs in a **Docker container**. The system supports CRUD operations for schools and students and maintains relationships between them.

---

## 🚀 Features  
- 🏢 **Manage Schools** - Add, view, update, and delete schools.  
- 🎓 **Manage Students** - Add, view, update, and delete students.  
- 💌 **Relation Handling** - Students belong to specific schools.  
- 🐟 **MongoDB in Docker** - Runs as a containerized service.  
- 👁️ **RESTful APIs** - Easily testable with cURL or Postman.

---

## 🛠️ Technologies Used  
- **Spring Boot** - Backend framework  
- **MongoDB** - NoSQL database  
- **Docker** - Containerized database  
- **Maven** - Dependency management  
- **cURL/Postman** - API testing  

---

## 🏢 Project Setup  

### **1⃣ Clone the Repository**  
```sh
git clone https://github.com/your-username/school-management-system.git
cd school-management-system
```

### **2⃣ Run MongoDB in Docker**  
Ensure **Docker** is installed and running, then start the MongoDB container:  
```sh
docker run -d --name mongodb-container -p 27017:27017 mongo
```
This will start a **MongoDB instance** in a **Docker container**.

### **3⃣ Configure Spring Boot**  
Modify the `application.properties` file:  
```properties
spring.data.mongodb.host=localhost
spring.data.mongodb.port=27017
spring.data.mongodb.database=schoolDB
```

### **4⃣ Build and Run the Application**  
```sh
mvn clean install
mvn spring-boot:run
```
Application will start on **http://localhost:8080/** 🚀  

---

## 📝 API Endpoints  

### 📌 **School Endpoints**  
| Method | Endpoint | Description |
|--------|---------|-------------|
| `POST` | `/schools` | Create a new school |
| `GET` | `/schools` | Get all schools |
| `GET` | `/schools/{id}` | Get a school by ID |
| `PUT` | `/schools/{id}` | Update a school |
| `DELETE` | `/schools/{id}` | Delete a school |

### 📌 **Student Endpoints**  
| Method | Endpoint | Description |
|--------|---------|-------------|
| `POST` | `/students` | Add a new student |
| `GET` | `/students` | Get all students |
| `GET` | `/students/{id}` | Get a student by ID |
| `PUT` | `/students/{id}` | Update a student |
| `DELETE` | `/students/{id}` | Delete a student |
| `GET` | `/schools/{schoolId}/students` | Get students of a specific school |

---

## 🛠️ **How to Test the APIs using cURL**  

### 🎓 **School API Testing**  

#### **Create a new school**  
```sh
curl -X POST http://localhost:8080/schools \
     -H "Content-Type: application/json" \
     -d '{
           "name": "Greenwood High",
           "address": "123 Main St"
         }'
```

#### **Get all schools**  
```sh
curl -X GET http://localhost:8080/schools
```

#### **Get a specific school by ID**  
```sh
curl -X GET http://localhost:8080/schools/{id}
```

#### **Update a school**  
```sh
curl -X PUT http://localhost:8080/schools/{id} \
     -H "Content-Type: application/json" \
     -d '{
           "name": "Updated School Name",
           "address": "456 New Address"
         }'
```

#### **Delete a school**  
```sh
curl -X DELETE http://localhost:8080/schools/{id}
```

---

### 🎓 **Student API Testing**  

#### **Add a new student**  
```sh
curl -X POST http://localhost:8080/students \
     -H "Content-Type: application/json" \
     -d '{
           "name": "John Doe",
           "age": 15,
           "schoolId": "{schoolId}"
         }'
```

#### **Get all students**  
```sh
curl -X GET http://localhost:8080/students
```

#### **Get a specific student by ID**  
```sh
curl -X GET http://localhost:8080/students/{id}
```

#### **Update a student**  
```sh
curl -X PUT http://localhost:8080/students/{id} \
     -H "Content-Type: application/json" \
     -d '{
           "name": "Updated Student",
           "age": 16,
           "schoolId": "{schoolId}"
         }'
```

#### **Delete a student**  
```sh
curl -X DELETE http://localhost:8080/students/{id}
```

#### **Get all students in a specific school**  
```sh
curl -X GET http://localhost:8080/schools/{schoolId}/students
```

---

## 🔥 Execution Summary  

1. **Set up MongoDB** in Docker (`docker run -d --name mongodb-container -p 27017:27017 mongo`)  
2. **Configure Spring Boot** to connect to MongoDB.  
3. **Run the Spring Boot application** (`mvn clean install && mvn spring-boot:run`).  
4. **Test API Endpoints** using cURL or Postman.  

---

## 📝 Conclusion  
This **School Management System** is a robust, scalable project utilizing **Spring Boot**, **MongoDB**, and **Docker**. The system effectively manages schools and students while ensuring easy deployment using containerized databases. APIs are well-structured and can be tested using **cURL/Postman**.

🚀 **Happy Coding!** 🎉

