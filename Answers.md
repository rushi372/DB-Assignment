Q1. Explain the relationship between the "Product" and "Product_Category" entities from the above diagram.
Answer -> The relationship between the "Product" and "Product_Category" entities is established through a foreign key in the "Product" table. The "category_id" column in the "Product" table serves as a foreign key referencing the "id" column in the "Product_Category" table. And this relationship is known as a many-to-one relationship.
Because each product in the "Product" table is associated with a category, and this association is maintained by storing the corresponding category's unique identifier (ID) in the "category_id" column of the "Product" table. By doing so, we can link a product to a specific category defined in the "Product_Category" table.
Example, if we have a "Mobile" product in the "Product" table, the "category_id" column for that product might contain the ID of the "Electronics" category from the "Product_Category" table. This helps us to organize and classify products into different categories, which facilitating better management and retrieval of information.

Q2. How could you ensure that each product in the "Product" table has a valid category assigned to it?
Answer -> To ensure that each product in the "Product" table has a valid category assigned to it, we can use a foreign key constraint. In the database schema, the "category_id" column in the "Product" table is used as a foreign key referencing the "id" column in the "Product_Category" table. 
Below query shows how to validate relationship between "Product" & "Product_Category" table,
ALTER TABLE Product
ADD CONSTRAINT fk_product_category
FOREIGN KEY (category_id)
REFERENCES Product_Category(id);
This SQL statement adds a foreign key constraint named "fk_product_category" to the "Product" table, specifying that the "category_id" column must match an existing "id" in the "Product_Category" table. This constraint ensures that we cannot insert a product with a "category_id" that does not exist in the "Product_Category" table.
If we attempt to insert or update a record in the "Product" table with an invalid "category_id," the database will reject the operation, maintaining the integrity of the relationship between the "Product" and "Product_Category" entities.
