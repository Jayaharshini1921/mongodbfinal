# Exp 7 CRUD Operations on Products Collection using MongoDB

**Date:**

## AIM:

To implement **CRUD (Create, Read, Update, and Delete) Operations using MongoDB** on a Products collection to store, retrieve, modify, and delete product information.

## DESIGN STEPS:

### Step 1:

Fork the given repository and clone the forked repository from GitHub.

### Step 2:

Open **MongoDB Shell (mongosh)** or MongoDB Compass and create a database for storing product information.

### Step 3:

Create a collection named **Products** with the fields **id, name, brand, price, category, stock,** and **tags**.

### Step 4:

Insert the following product records into the Products collection.

| id | name       | brand    | price | category    | stock | tags                       |
| -- | ---------- | -------- | ----: | ----------- | ----: | -------------------------- |
| 1  | Laptop     | Dell     | 55000 | Electronics |    30 | ["computer", "technology"] |
| 2  | Smartphone | Samsung  | 30000 | Electronics |    50 | ["mobile", "android"]      |
| 3  | Headphones | Sony     |  2500 | Accessories |   100 | ["audio", "music"]         |
| 4  | Smartwatch | Apple    | 45000 | Electronics |    20 | ["wearable", "ios"]        |
| 5  | Keyboard   | Logitech |  1200 | Accessories |    80 | ["computer", "typing"]     |

### Step 5:

Perform the **Create operation** by inserting all the given product documents into the Products collection.

### Step 6:

Perform the **Read operation** to display all the documents available in the Products collection.

### Step 7:

Retrieve products based on conditions such as **product ID, category, price, brand, stock,** and **tags**.

### Step 8:

Perform the **Update operation** to modify selected product information such as **price, stock,** or **tags**.

### Step 9:

Perform an update operation on multiple documents belonging to a particular product category.

### Step 10:

Perform the **Delete operation** to remove a selected product document from the Products collection.

### Step 11:

Display the final Products collection and verify the changes made through the CRUD operations.

### Step 12:

Execute all the MongoDB commands, capture the required outputs, commit the completed experiment, and push the changes to the forked GitHub repository.

## PROGRAM:

*// Create database
use mydb

// Create collection
db.createCollection("products")

// Insert all products
db.products.insertMany([
  {
    _id: 1,
    name: "Laptop",
    brand: "Dell",
    price: 55000,
    category: "Electronics",
    stock: 30,
    tags: ["computer", "technology"]
  },
  {
    _id: 2,
    name: "Smartphone",
    brand: "Samsung",
    price: 30000,
    category: "Electronics",
    stock: 50,
    tags: ["mobile", "android"]
  },
  {
    _id: 3,
    name: "Headphones",
    brand: "Sony",
    price: 2500,
    category: "Accessories",
    stock: 100,
    tags: ["audio", "music"]
  },
  {
    _id: 4,
    name: "Smartwatch",
    brand: "Apple",
    price: 45000,
    category: "Electronics",
    stock: 20,
    tags: ["wearable", "ios"]
  },
  {
    _id: 5,
    name: "Keyboard",
    brand: "Logitech",
    price: 1200,
    category: "Accessories",
    stock: 80,
    tags: ["computer", "typing"]
  }
])

// Read all documents
db.products.find().pretty()

// Read products below 5000
db.products.find({
  price: { $lt: 5000 }
})

// Read only accessories
db.products.find({
  category: "Accessories"
})

// Read electronics below 50,000
db.products.find({
  $and: [
    { category: "Electronics" },
    { price: { $lt: 50000 } }
  ]
})

// Update laptop price
db.products.updateOne(
  { name: "Laptop" },
  { $set: { price: 52000 } }
)

// Increase keyboard stock by 10
db.products.updateOne(
  { name: "Keyboard" },
  { $inc: { stock: 10 } }
)

// Add premium tag to smartwatch
db.products.updateOne(
  { name: "Smartwatch" },
  { $push: { tags: "premium" } }
)

// Delete Keyboard
db.products.deleteOne({
  name: "Keyboard"
})*

## OUTPUT:

<img width="819" height="94" alt="643231602-f2080e4c-79d4-4ee2-915a-ba3d507cb604" src="https://github.com/user-attachments/assets/7fa4d65e-9d4f-4447-b74e-41702f0d072d" />
<img width="601" height="806" alt="643231610-a76c3589-34b6-4eda-b3fc-e7f00e449a2c" src="https://github.com/user-attachments/assets/2c23f487-b91c-465e-9e50-4b33484b9e05" />
<img width="839" height="483" alt="643231622-a7199b83-724f-4b72-9e10-1829cf7c245f" src="https://github.com/user-attachments/assets/e8816873-4355-4486-8bc7-7d6f671ca804" />
<img width="840" height="485" alt="643231627-57f983b2-b1ad-4f1a-93bd-2f095c6733c5" src="https://github.com/user-attachments/assets/e4bd6e0b-df10-4d5d-9a43-93d2a10fc16e" />
<img width="828" height="466" alt="643231636-a221790c-62b0-4654-a633-71b85acad5db" src="https://github.com/user-attachments/assets/2d15abed-a661-463a-8f4f-c74deea40290" />
<img width="630" height="800" alt="643231644-988cb312-02ca-4ed7-94f3-28a9c9f05754" src="https://github.com/user-attachments/assets/cf76ef14-073d-4fe9-a682-adae558d1a34" />
<img width="633" height="648" alt="643231653-4d9fdd53-0fe8-4368-ac3f-f074755b8612" src="https://github.com/user-attachments/assets/6bebf151-f1d1-4c22-8cfe-d52f85bd5d51" />


## RESULT:

The **CRUD Operations on the Products Collection using MongoDB** were implemented successfully. The product documents were created, retrieved, updated, and deleted using appropriate MongoDB commands, and the final changes were successfully verified in the Products collection.
