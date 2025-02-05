# Ruby on Rails - my first application

My first Ruby on Rails app and my first exposure to Ruby. Made using the [Getting Started with Rails guide](https://guides.rubyonrails.org/getting_started.html). Developed on Ubuntu 22 (via WSL) with Ruby 3 and Rails 8. Rails is a web server that uses the MVC architecture. 

### First impressions

I find the Ruby language pretty strange because I've never used anything like it.

Rails has some similar patterns to Django but things have different names, for example a Rails view is like a Django template, and a Rails controller is like a Django view. Ruby doesn't try to abstract the SQL as heavily as Django, for instance: result set operation names mirror the underlying SQL keyword (e.g. `where`).

Perhaps the strangest thing with Rails is that model and field definitions are nowhere to be seen in the code. It looks like you have to check the database via the Rails console to find out what fields your models have; or, you can look through the migration scripts to work out what was added and removed. The reason for this pattern is to reduce boilerplate, which is apparently central to the Rails philosophy of Convention over configuration.

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
  - Query records with a filter like this: `Product.where(name: "Jeans")`
  - Sort records like this: `Product.order(name: :asc)`
  - Find specific records like this: `product = Product.find(1)`
  - Then update it like this: `product.update(name: "Shoes")`
  - The record can also be updated this way: `product.name = "Socks"` followed by `product.save`
  - Delete a record like this: `product.destroy`
  - After making changes, such as adding validation (e.g. the presence validation at app/models/product.rb), the console needs to be reloaded like this: `reload!`
  - Saving a record only works if validation passes. Validate and see a list of errors like this: `product.errors`
  - For a more detailed validation error, use: `product.errors.full_messages`
- Create a controller with an index view for the Products model with `bin/rails generate controller Products index --skip-routes`

### Progress

My progress through the guide:
- [x] App creation
- [x] Models and migrations
- [x] Rails console
- [x] Routes
- [x] Controllers, controller actions and views
- [ ] Authentication
- [ ] Caching
- [ ] Action Text
- [ ] Active Storage
- [ ] Internationalisation
- [ ] Email notifications
- [ ] Propshaft for CSS and JavaScript
- [ ] Testing
- [ ] Rubocop for linting
- [ ] Security
- [ ] GitHub Actions for CI
- [ ] Deploying to production