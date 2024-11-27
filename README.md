# .Net & MongoDB Application
This project is a 3-tier web application built with .NET and MongoDB. The application consists of a presentation layer, a business logic layer, and a data access layer. MongoDB is used as the database to store and manage application data.

## Pre-requisites

Before setting up the project, ensure you have the following softwares installed on your Ubuntu(24.04 LTS) Machine:

[.Net SDK 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
[MongoDB 7.0](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/?msockid=0df078bf170f66e03cf26dba16bd6741)

## Installation

### 1. Installing .NET SDK and Runtime

To install the .NET SDK & Runtime, execute the following commands in your terminal:

```bash
# update the package manager
sudo apt update && sudo apt install -y dotnet-sdk-8.0 aspnetcore-runtime-8.0
```

### 2. Installing MongoDB
1. To install MongoDB, execute the following commands in your terminal:

    ```bash
    sudo apt-get update && sudo apt-get install gnupg curl -y

    curl -fsSL https://www.mongodb.org/static/pgp/server-8.0.asc | \
       sudo gpg -o /usr/share/keyrings/mongodb-server-8.0.gpg \
       --dearmor

    echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-8.0.gpg ] https://repo.mongodb.org/apt/ubuntu noble/mongodb-org/8.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.0.list

    sudo apt-get update && sudo apt-get install -y mongodb-org mongodb-mongosh

    sudo systemctl start mongod
    sudo systemctl enabled mongod
    ```

2. **Access MongoDB Terminal:**  
To interact with your MongoDB instance, open the MongoDB shell using:
   ```bash
   mongosh
   ```

3. **Manipulate Databases and Collections:**

 - Show databases:
   ```bash
   show dbs;
   ```
 - Use a specific database:
   ```bash
   use db_name; # mention your databaseName
   ```
 - Show collections in the database:
   ```bash
   show collections;
   ```
 - Query the `Products` collection:
   ```bash
   db.Products.find().pretty();
   ```


## Running the Application

To run the .NET Application
1. Navigate to the root directory where `.cs` or `.sln` or `.csproj` is located
2. Restore the dependencies:
   ```bash
   dotnet restore
   ```
3. Build the Application
   ```bash
   dotnet build -c Release
   ```
4. Run the application
   ```bash
   dotnet run
   ```
The application will start, and you can access it in your web browser.

Access the app and manipulate the data through the UI,


## Using MongoDB Shell

To manipulate your MongoDB database using MongoDB Shell:

1. **Start the shell:**

   ```bash
   mongosh
   ```

2. **Example commands:**

  - **List all databases:**
    ```bash
    show dbs;
    ```
  - **Switch to a specific database:**
    ```bash
    use db_name;
    ```
  - **Show collections in the current database:**
    ```bash
    show collections;
    ```
  - **Find all documents in a collection:**
    ```bash
    db.Products.find().pretty();
    ```