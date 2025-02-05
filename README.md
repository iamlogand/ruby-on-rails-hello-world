# Ruby on Rails - Hello World application

My first Ruby on Rails app and first exposure to Ruby, made using https://guides.rubyonrails.org/getting_started.html. Developed on Ubuntu 22 (running on WSL) with Ruby 3 and Rails 8. Rails is a web server that uses the MVC architecture.

### Main commands learned

- Create a new app called "store" with `rails new store`
- Start the server with `bin/rails server`
- Create new model named "Product" with a string field named "name" with `bin/rails generate model Product name:string`
- Run a migration with `bin/rails db:migrate`
- Run the Rails console with `bin/rails console`. In the console, you can...
  - Get columns for a model called Product with `Product.column_names`
  - Create a new record like this: `product = Product.new(name: "T-Shirt")`
  - Then save it like this: `product.save`
  - Create and save can be performed in a single call: `Product.create(name: "Jeans")`
  - Query records like this: `Product.all`
  - Query records with a filer like this: `Product.where(name: "Jeans")`
  - Find specific records like this: `product = Product.find(1)`
  - Then update it like this: `product.update(name: "Shoes")`
  - The record can also be updated this way: `product.name = "Socks"` followed by `product.save`
  - Delete a record like this: `product.destroy`
  - After making changes, such as adding validation (e.g. the presence validation at app/models/product.rb), the console needs to be reloaded like this: `reload!`
  - Saving a record only works if validation passes. Validate and see a list of errors like this: `product.errors`
  - For a more detailed validation error, use: `product.errors.full_messages`
- Create a controller with an index view for the Products model with `bin/rails generate controller Products index --skip-routes`
