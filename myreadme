// MongoDB Fundamentals Assignment

// Step 1: Setup MongoDB
// Verify installation
// Run in terminal: mongo --version

// Step 2: Create a database and collection
use library;
db.createCollection("books");

// Step 3: Insert book records
db.books.insertMany([
    { title: "The Great Gatsby", author: "F. Scott Fitzgerald", publishedYear: 1925, genre: "Fiction", ISBN: "9780743273565" },
    { title: "To Kill a Mockingbird", author: "Harper Lee", publishedYear: 1960, genre: "Fiction", ISBN: "9780061120084" },
    { title: "1984", author: "George Orwell", publishedYear: 1949, genre: "Dystopian", ISBN: "9780451524935" },
    { title: "The Catcher in the Rye", author: "J.D. Salinger", publishedYear: 1951, genre: "Fiction", ISBN: "9780316769488" },
    { title: "The Road", author: "Cormac McCarthy", publishedYear: 2006, genre: "Post-Apocalyptic", ISBN: "9780307387899" }
]);

// Step 4: Retrieve Data
// Retrieve all books
db.books.find();

// Query books based on a specific author
db.books.find({ author: "George Orwell" });

// Find books published after the year 2000
db.books.find({ publishedYear: { $gt: 2000 } });

// Step 5: Update Data
// Update the publishedYear of a specific book
db.books.updateOne({ title: "1984" }, { $set: { publishedYear: 1950 } });

// Add a new field called rating to all books and set a default value
db.books.updateMany({}, { $set: { rating: 5 } });

// Step 6: Delete Data
// Delete a book by its ISBN
db.books.deleteOne({ ISBN: "9780451524935" });

// Remove all books of a particular genre
db.books.deleteMany({ genre: "Fiction" });

// Step 7: Data Modeling for an e-commerce platform
db.createCollection("users");
db.createCollection("orders");
db.createCollection("products");

// Sample structure for users
db.users.insertOne({ name: "John Doe", email: "johndoe@example.com", address: "123 Main St" });

// Sample structure for products
db.products.insertOne({ name: "Laptop", price: 1200, category: "Electronics" });

// Sample structure for orders
db.orders.insertOne({ userId: ObjectId("someUserId"), productId: ObjectId("someProductId"), quantity: 1 });

// Step 8: Aggregation Pipeline
// Find the total number of books per genre
db.books.aggregate([ { $group: { _id: "$genre", totalBooks: { $sum: 1 } } } ]);

// Calculate the average published year of all books
db.books.aggregate([ { $group: { _id: null, avgPublishedYear: { $avg: "$publishedYear" } } } ]);

// Identify the top-rated book
db.books.aggregate([ { $sort: { rating: -1 } }, { $limit: 1 } ]);

// Step 9: Indexing
// Create an index on the author field
db.books.createIndex({ author: 1 });

// Step 10: Testing
// Use MongoDB shell or Compass to verify inserted and updated records
