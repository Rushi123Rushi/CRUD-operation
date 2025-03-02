# CRUD-operation
The extracted project contains the necessary components, including:

Spring Boot setup (CurdApplication.java)
REST Controllers (CategoryController.java, ProductController.java)
Entity models (Category.java, Product.java)
JPA Repositories (CategoryRepository.java, ProductRepository.java)
Service layer (CategoryService.java, ProductService.java)
Database configuration (application.properties)
Maven build files (pom.xml)
I'll now check if the implementation satisfies all your specific requirements. ​​

The project is correctly configured to use a relational database (MySQL) instead of an in-memory database, which meets the requirement. Now, I'll verify the entity relationships, CRUD operations, and pagination support. ​​

The Category and Product entities are correctly configured with JPA annotations:

Category:

Marked with @Entity
Has @OneToMany with cascade = CascadeType.ALL for related products
Uses @JsonIgnore to avoid infinite recursion in serialization
Product:

Marked with @Entity
Has @ManyToOne with @JoinColumn(name = "category_id", nullable = false), establishing the one-to-many relationship with Category.
Now, I'll check the controller methods for CRUD operations and pagination support. ​​

The CategoryController and ProductController include all necessary CRUD operations:

Category APIs:

@GetMapping (Fetch all categories)
@GetMapping("/{id}") (Fetch category by ID)
@PostMapping (Create category)
@PutMapping("/{id}") (Update category by ID)
@DeleteMapping("/{id}") (Delete category by ID)
Product APIs:

@GetMapping (Fetch all products)
@GetMapping("/{id}") (Fetch product by ID, should include category details)
@PostMapping (Create product)
@PutMapping("/{id}") (Update product by ID)
@DeleteMapping("/{id}") (Delete product by ID)
Now, I'll confirm if pagination is implemented in the GET methods. ​​

Pagination is correctly implemented in both controllers:

Page and Pageable are imported.
The getAllCategories(Pageable pageable) and getAllProducts(Pageable pageable) methods handle pagination.
Final Verification Summary
✅ Spring Boot used
✅ REST Controllers implemented
✅ Relational Database (MySQL) configured
✅ Annotation-based configuration (No XML)
✅ JPA & Hibernate used
✅ Category CRUD operations implemented
✅ Product CRUD operations implemented
✅ One-to-Many relationship between Category and Product
✅ Server-side pagination implemented
✅ Fetching a single product includes category details

Your project meets all the specified requirements.
