[Epicodus Cliff Notes](http://www.learnhowtoprogram.com/table-of-contents)
====================

## Table of Contents

* [Simple web pages]
* [HTML and CSS basics]
* [JavaScript primitives, methods, and functions]
* [jQuery]
* [Branching and looping in JavaScript]
* [Programming basics with JavaScript]
* [Behavior-driven development]
* [Object-oriented design]
* [Programming basics with Ruby]
* [Ruby syntax and TDD]
* [OO with Ruby]
* [Databases](#databases)
* [Database basics](#database-basics)
* [SQL basics](#sql-basics)
* [Using SQL with Ruby](#using-sql-with-ruby)
* [To do list with SQL](#to-do-list-with-sql)
* [Git](#git)
* [Join statements](#join-statements)
* [Databases with Active Record](#databases-with-active-record)
* [Inheritance and modules](#inheritance-and-modules)
* [Set up a project using Active Record](#set-up-a-project-using-active-record)
* [Bundler](#bundler)
* [Active Record validations and callbacks](#active-record-validations-and-callbacks)
* [Web applications](#web-applications)
* [Ruby on Rails with minimal magic](#ruby-on-rails-with-minimal-magic)
* [Rails setup, database, models](#rails-setup-database-models)
* [Rails routing, controllers, views](#rails-routing-controllers-views)
* [Better parameters](#better-parameters)
* [Conventional Rails]
* [Rails with AJAX]


## Databases
###Database basics
  **Database relations:**
  Three types of relationships:
  *One-to-many* (e.g., a course has many students, and a student belongs to one course - like Epicodus)
  *Many-to-many* (e.g., a course has many students, and a student has many courses - like college)
  *One-to-one* (a tutor who only serves a single client)

  [SQL Designer website](http://ondras.zarovi.cz/sql/demo/)

###SQL basics:
Common SQL commands:

```console
CREATE DATABASE database_name;
CREATE TABLE table_name (id serial PRIMARY KEY, some_column varchar, another_column int, yet_another_column timestamp);
ALTER TABLE table_name ADD column_name boolean;
ALTER TABLE table_name DROP column_name;
INSERT INTO contacts (name, age, birthday) VALUES ('Wes', 43, '1969-05-01') RETURNING id;
SELECT * FROM table_name WHERE age >= 18;
UPDATE contacts SET name = 'Wes Anderson' WHERE id = 1;
DELETE FROM contacts WHERE id = 1;
DROP TABLE table_name;
DROP DATABASE test_database;
```

Common psql commands:

* List all databases: `\l`
* Connect to database: `\c database_name`
* List tables in current database: `\dt`
* List columns in a table: `\d table_name`

Common column types:
```console
int
float
varchar
text (for long strings of text)
timestamp
boolean
```
Operators for WHERE clauses:
```console
=
!=
>
<
>=
<=
BETWEEN
LIKE
IN
```
###Using SQL with Ruby

Connect to a database:
```console
some_db = PG.connect({:dbname => 'some_db'})
```

Run SQL:
```console
some_db.exec("INSERT INTO contacts (name) VALUES ('michael');")
The results are a collection of hashes:
results = address_book_db.exec("SELECT * FROM contacts;")
results.each { |result| p result }
results.each { |result| p result.class } #each result is a hash
```
###To do list with SQL
If you find yourself using SQL without Active Record, then go [here](http://www.learnhowtoprogram.com/lessons/to-do-list-with-sql).
Here's the link to [PostgreSQL documentation](http://www.postgresql.org/docs/9.2/static/queries-order.html)

**CRUD:** stands for Create, Read, Update, and Destroy

###Git
Getting to know Git, getting to know all about Git - check out the first two chapters. http://teamtreehouse.com/library/git-basics

Branching and merging information starts on the third chapter, appropriately called Branches.

###Join Statements
Join statement (not a join table):
```console
SELECT * FROM
animals JOIN trainers ON (animals.trainer_id = trainers.id)
WHERE trainers.id = 1;
```

3-table join
```console
  select animals.* from
  trainers join lessons on (trainers.id = lessons.trainer_id)
            join animals on (lessons.animal_id = animals.id)
  where trainers.id = 1;
```
##Databases with Active Record
###Inheritance and modules
Find an object’s class: ex. `5.class`

When one class inherits from another, it has all of the methods available to it from the parent class. Every class inherits from Object. Object inherits from BasicObject. BasicObject inherits from nil.

See the methods on an object: ex. `3.methods`
Remove methods all objects have: ex. `3.methods - Object.new.methods`

Modules are collections of methods and constants that can be included in any class.

###Set up a project to use Active Record:
* Install Active Record: `$ gem install activerecord`
* Install Rake: `$ gem install rake`
* Install Active Record Migrations: `$ gem install active_record_migrations`
* Create a db folder in your project directory
* Create a file called Rakefile in your project directory and add this to it:
```console
require ‘active_record_migrations’
ActiveRecordMigrations.load_tasks
```
* Create a file in db called config.yml and add this to it:
```console
development:
  adapter: postgresql
  database: project_name_development
test:
  adapter: postgresql
  database: project_name_test
```
Common one-off database tasks:
* Create your test and development databases: `$ rake db:create`
* Drop your databases: `$ rake db:drop`
* Create an empty migration: `$ rake db:new_migration name=descriptive_migration_name`
* Run a migration: `$ rake db:migrate`
* Roll back a mibration: `$ rake db:rollback`
* Prepare your test database: `$ rake db:test:prepare` (might be depracated...)

**Migration Guide:**
Here’s the [Ruby on Rails guide for Active Record Migrations](http://guides.rubyonrails.org/migrations.html) - it will help remind you of what is needed to update your schema in exactly the way you want it.

And, the [Rails API documentation on migrations](http://api.rubyonrails.org/classes/ActiveRecord/Migration.html)

Active Record queries and associations
[Rails Guide on querying conditions](http://guides.rubyonrails.org/active_record_querying.html#conditions)

[Rails API documentation on query methods](http://api.rubyonrails.org/classes/ActiveRecord/QueryMethods.html)

[Rails Guide on Active Record associations](http://guides.rubyonrails.org/association_basics.html)

[Rails API documentation on associations](http://api.rubyonrails.org/classes/ActiveRecord/Associations/ClassMethods.html)

###Bundler
* Run `$ bundle`, when you’ve got your Gemfile all set up with the necessary gems
* Run `$ gem regenerate_binstubs`, if you get an error about using the wrong version of a gem.

###Active Record validations and callbacks
* ex. of tests for validations:
```console
describe Task do
  it { should validate_presence_of :name }
  it { should ensure_length_of(:name).is_at_most(50) }
end
```
* ex. of how the model would look:
```console
class Task < ActiveRecord::Base
  validates :name, :presence => true, :length => { :maximum => 50 }
end
```
* ex. of callback:
```console
class Task < ActiveRecord::Base
  before_save :downcase_name

private

  def downcase_name
    self.name = self.name.downcase
  end
end
```
[Rails Guide on validations](http://guides.rubyonrails.org/active_record_validations.html#exclusion)

[Rails API documentation on validations](http://api.rubyonrails.org/classes/ActiveModel/Validations/ClassMethods.html)

[Rails Guide on callbacks](http://guides.rubyonrails.org/active_record_callbacks.html)

[Rails API documentation on callbacks](http://api.rubyonrails.org/classes/ActiveRecord/Callbacks.html)

###Shoulda-matchers
It’s a gem that helps to make validations, and callbacks more condensed - here’s the [documentation](https://github.com/thoughtbot/shoulda-matchers) for it.

###Polymorphic Associations
Here’s the [Rails Guide to polymorphism](http://guides.rubyonrails.org/association_basics.html#polymorphic-associations)

###Validates_timeliness
[This gem](https://github.com/adzap/validates_timeliness) is a date and time validation plugin for ActiveRecord and Rails. It supports ORMs (Object Relational Mapper) and allows custom date/time formats - it doesn’t currently support much in terms of testing.

###Textacular
[This gem](https://github.com/textacular/textacular) exposes full text search capabilities from PostgreSQL.

###Indexes for your database:
Here’s a [great article](http://robots.thoughtbot.com/a-grand-piano-for-your-violin) on the power of indexes and how it will change the way you use databases.

###Cloning a repo from Github:
Grab the link from the bottom right of the chosen Github page, and run
```console
$ git clone https://github.com/… (<- replace the url with the appropriate link)
```
To load the current schema all at once (in case there’s loads of migrations in the project), run `$ rake db:schema:load`. It’s much faster and less error prone.

**DRY:** Stands for Don’t Repeat Yourself

**Scopes:**
This is similar to the WHERE statements from back in PostgreSQL days. Here’s two examples of workable scopes:

* ex. 1 - passing through an argument:
```console
class Musician < ActiveRecord::Base
  scope :find_by_instrument, -> (instrument) { where(instrument_id: instrument.id) }
end
```
* ex. 2 - no argument
```console
class Task < ActiveRecord::Base
  scope :completed, -> { where(completed: true) }
end
```

Here’s [more information on Scopes](http://guides.rubyonrails.org/active_record_querying.html#scopes)

##Web Applications
###Ruby on Rails with minimal magic
  **How the web works**

* **HTTP:** stands for Hypertext Transfer Protocol
* HTTP uses a client-server model, where a client sends a request, and a server provides a response. Web browsers are clients.
* A request includes a method (also called a verb), a path, headers, and a body.
* Methods indicate the the type of action.
* The path is the URL, like:
`http://www.epicodus.com/students.html`.
* Headers include optional information, like format or authentication.
* The body includes information like the contents of a form.

**Common HTTP methods:**
* **GET** retrieves information without changing anything on the server.
* **POST** creates something.
* **PATCH** or **PUT** updates.
* **DELETE** destroys.
* Responses include status, headers, and body.
* The status is a three-digit code that represents the outcome of the request.
* Headers might include content type or redirect location.
* The body includes the actual HTML, CSS, JavaScript, etc.

**Common statuses:**
```console
200 OK (successful)
201 Created
301 Moved Permanently
302 Moved Temporarily
400 Bad Request
403 Forbidden (it exists but you aren't allowed to see it)
404 Not Found
422 Unprocessable Entity (you put in bad data)
500 Internal Server Error
502 Bad Gateway (the server sent the request to another server and got an invalid response)
503 Service Unavailable (the server is overloaded or down for maintenance)
```
###Rails setup, database, models
* Rails uses the model-view-controller pattern:
* The router parses the request and passes it to a controller.
* Controllers tell the model to do some work and then render a view.
* Models embody the application logic, and can be plain Ruby objects or inherit from Active Record.
* Views are HTML with some Ruby sprinkled in.

* Create a file called '.railsrc' in your home directory and type `-d postgresql -T`.
* Make a new Rails app: `$ rails new your_app_name`
* Example of what your config/database.yml might look like:
```console
development:
   adapter: postgresql
    database: wikipages_development
test:
    adapter: postgresql
    database: wikipages_test
```
* To create a new migrations, run: `$ rails g migration your_migration_name`
* To Set up RSpec, run: `$ rails generate rspec:install`
* To get an IRB shell with the Rails development environment loaded, including gems and models, run: `$ rails console`

**Comprehensive Gemfile Example** (please remember to look up gems if you don’t know what they do):

```console
source 'https://rubygems.org'

gem 'rails'
gem 'pg'
gem 'sass-rails'
gem 'uglifier'
gem 'coffee-rails'
gem 'jquery-rails'
gem 'turbolinks'
gem 'jquery-turbolinks'
gem 'bcrypt', '~> 3.1.5'
gem 'bootstrap-sass', '~> 3.2.0'
gem 'autoprefixer-rails'
gem 'devise'
gem 'simple_form'

group :development do
    gem 'better_errors'
    gem 'binding_of_caller'
    gem 'quiet_assets'
end

group :test, :development do
    gem 'rspec-rails'
    gem 'pry'
    gem 'launchy’
    gem 'rest_client’
    gem 'dotenv-rails’
end

group :test do
    gem 'shoulda-matchers'
    gem 'factory_girl_rails’
    gem 'capybara’
    gem 'webmock’
end

group :production do
    gem 'rails_12factor’
end
```
###Rails routing, controllers, views
* To start the local Rails server, run: `$ rails server`, or `$ rails s`
* View your app at http://localhost:3000

**7 RESTful actions** (stands for Representational State Transfer):
```console
GET (index)
GET (new)
POST (create)
GET (show)
GET (edit)
PUT/PATCH (update)
DELETE (destroy)
```
Your RESTful actions will live in your controllers. If you feel the need to create another method, your model is a good place for that!

What “resources :contacts” does in your routes.rb file:
```console
Wikipages::Application.routes.draw do
    match('contacts', {:via => :get, :to => 'contacts#index'})
    match('contacts/new', {:via => :get, :to => 'contacts#new'})
    match('contacts', {:via => :post, :to => 'contacts#create'})
    match('contacts/:id', {:via => :get, :to => 'contacts#show'})
    match('contacts/:id/edit', {:via => :get, :to => 'contacts#edit'})
    match('contacts/:id', {:via => [:patch, :put], :to => 'contacts#update'})
    match('contacts/:id', {:via => :delete, :to => 'contacts#destroy'})
end
```
###Better parameters
Changing this,:
```console
@contact = Contact.new( :name => params[:name],
                        :phone => params[:phone],
                        :email => params[:email])
```
to this:
```console
    def new
        @contact = Contact.new(contact_params)
    end

private
    def contact_params
        params.require(:contact).permit(:name, :phone, :email)
    end
end
```
  Heroku
  Watch the screencast on how to put your Rails sites online:
https://www.codeschool.com/code_tv/heroku

Make sure heroku-toolbelt is installed ($ brew install heroku-toolbelt, if your on a Mac)

Make sure your Gemfile includes the gem ‘rails_12factor’ in your :production group.

When starting on a new computer, generate a new pair of SSH keys:
  $ ssh-keygen -t rsa -C your_email@address.com

Run:  $ heroku login
  $ heroku keys:add

Set up your Heroku app
If you haven’t created a Heroku app yet, run: $ heroku create your_app_name
If you’ve already created a Heroku app, run: $ heroku git:remote -a your_app_name
  Push your code to Heroku with: $ git push heroku master
  To migrate your database, run: $ heroku run rake db:migrate
  If you want to add a team member:
$ heroku sharing:add your_friends_email#their_address.com

If you get the error “Permission denied (publickey), run $ rm ~/.ssh/* to clear the SSH settings off the machine, then start the process again with adding a new pair of SSH keys.
Redirecting
redirect_to:
should be used after successful create, update, and destroy;
takes a URL as its argument;
causes the browser to make an entirely new request.

render:
should be used after unsuccessful creates and updates, so that the problematic information can be displayed on the screen to be fixed;
takes a view as an argument;
simply returns HTML as a response to the current request.

The layout
If you want to have every page list a different title, add this to your app/views/layouts/application.html.erb file: <title><%= yield(:title) %></title>

On your other view pages, add something like this:
<% content_for(:title, "New contact | Wikipages") %>
If your wanting your navbar to change depending on the view, try this:
<% content_for(:navbar) do %>
<li><a href="/">Home</a></li>
<li><a href="something/else">Something else</a></li>
<li><a href="etc">Etc.</a></li>
<% end %>

Flash messages
You can add flash messages to your controller methods, like this:

class ContactsController < ApplicationController
def create
@contact = Contact.new(params[:contact])
      if @contact.save
flash[:notice] = "Your contact was added to Wikipages."
        redirect_to("/contacts/#{@contact.id}")
else
        render('contacts/new.html.erb')
end
end
end

  Just remember to add this to your app/views/layouts/application.html.erb file, in the
<body>:

<%= flash[:alert] %>
<%= flash[:notice] %>

Partials
Partials allow you to render chunks of code that you would otherwise be repeating.
Here’s the errors partial we’ve been using (make a file _errors.html.erb in your view/layouts folder):
<% if object.errors.any? %>
      <h3>Please fix these errors:</h3>
      <ul>
      <% object.errors.full_messages.each do |message| %>
         <li><%= message %></li>
      <% end %>
      </ul>
<% end %>

  This is how you would render the _errors.html.erb partial on your views page:
    <%= render('layouts/errors', :object => @contact) %>
  Sass, the asset pipeline, and Bootstrap
Michael’s reference for this is more comprehensive than I can make cliff notes for, so
here’s the link that that page, for quick look-up:
http://www.learnhowtoprogram.com/lessons/sass-the-asset-pipeline-and-bootstrap

Conventional Rails
  Magic methods
  This is where we changed our routes from “match” to “resources. Here’s an example
of what that looks like (config/routes.rb):

Wikipages::Application.routes.draw do
    resources :contacts do
        resources :phones, :only => [:new, :create]
    end

    resources :phones, :except => [:new, :create]
end

To see your routes, run: $ rake routes

You can now use the route paths in your controller, here’s an example of that:

   def create
        @contact = Contact.new(params[:contact])
        if @contact.save
            flash[:notice] = "Contact created."
            redirect_to contacts_path
        else
            render 'new'
        end
   end

Writing links with helpers:
<%= link_to "New contact", new_contact_path, :class=> "btn btn-default" %>
Deleting with helper links:
<p><%= link_to "Delete", contact_path(@contact),
                         :data => {:confirm => "You sure?",
                                   :method => "delete"},
                         :class => "btn btn-danger" %></p>

Writing forms with helpers:
<%= form_for(@contact) do |f| %>
      <div class="form-group">
          <%= f.label :name %>
          <%= f.text_field :name %>
      </div>
     <div class="form-group">
          <%= f.label :phone %>
          <%= f.text_field :phone %>
     </div>
      <div class="form-group">
         <%= f.label :email %>
          <%= f.text_field :email %>
     </div>
      <%= f.submit(:class => "btn btn-primary") %>
<% end %>

Security basics
CSRF: stands for Cross-Site Request Forgery. Here's how CSRF works:
You log into your bank account at www.bank.com and a cookie is placed on your computer to identify you.
You don't log out, and then you visit a chat board. The cookie remains on your computer.
On the chat board, a malicious user could then write some code to nab your cookie and wreak havoc with your bank account.
To keep this from happening, Rails creates an autenticity token. “form_for” automatically adds tokens to your forms. HTML forms should include something like this:
<input name="authenticity_token" type="hidden" value="c6j4CiHdGCJ5NcjWXvEQXGIsjCbrKQ4zpJYcyhCWn9E=" />
Also, make sure that “protect_form_forgery with: :exception” is turned on in your ApplicationController.
Mass assignment
Check out Treehouse’s blog on Strong Parameters: http://blog.teamtreehouse.com/rails-4-strong-paremeters

There’s a RailsCast video on this too, if you have access to an account:
http://railscasts.com/episodes/26-hackers-love-mass-assignment-revised

SQL injection
Read all about it! (right here): http://guides.rubyonrails.org/security.html#sql-injection

Ruby drop-down menu code
Ex. <%= f.collection_select :station_id, Station.all, :id, :name %>
Ruby checkboxes
Here’s the documentation: http://edgeapi.rubyonrails.org/classes/ActionView/Helpers/FormBuilder.html#method-i-collection_check_boxes
Capybara
This is a testing tool, similar to mocha and chai, that allows a developer to test the flow of their application. Here’s how you can get started with Capybara:

Install ‘capybara’ in your Gemfile, and require ‘capybara’ in your rails_helper
Create a “features” folder in your spec folder

  Here’s the documentation on Capybara:
Capybara README: https://github.com/jnicklas/capybara
Using Capybara with RSPEC: https://github.com/jnicklas/capybara#using-capybara-with-rspec

  Remember to use the launch gem to make debugging in Capybara loads easier:
  https://github.com/copiousfreetime/launchy

  Authentication
You can create a user authentication from scratch, if you like. There’s a RailsCast video on this, if you have access to it: http://railscasts.com/episodes/250-authentication-from-scratch-revised

Otherwise, you can create user authentication using the Devise gem: https://github.com/plataformatec/devise/
Here’s how you would go about doing that:

$ rails g devise:install
$ rails g devise user
$ rake db:migrate
$ rails g devise:views

Add gem ‘devise’ to your Gemfile. Don’t forget to run $ bundle and restart your server.

Add this to your config/environments/development.rb file:
config.action_mailer.default_url_options = { :host => 'localhost:3000' }

  Here’s a good example of the links to sign in paths, to be added onto your
layouts/application.html.erb file (either directly on the file or through a partial):
<% if user_signed_in? %>
  Logged in as <strong><%= current_user.email %></strong>
    <%= link_to 'Edit profile', edit_user_registration_path %> |
    <%= link_to "Logout", destroy_user_session_path, method: :delete %>
<% else %>
    <%= link_to "Sign up", new_user_registration_path %> |
    <%= link_to "Login", new_user_session_path %>
<% end %>

Make sure your config/routes.rb looks something like this:
devise_for :users, path_names: {sign_in: "login", sign_out: "logout"}

  Add something similar like this to your class controller pages:
before_filter :authenticate_user!, except: [:index, :show]

  Polymorphism
  This is in reference to the whole commenting on comments thang in the Hacker News
clone project. Here’s the documentation on polymorphic associations:
http://guides.rubyonrails.org/association_basics.html#polymorphic-associations

Your associations will look something like this:
class Comment < ActiveRecord::Base
    belongs_to :commentable, :polymorphic => true
    has_many :comments, :as => :commentable
end

class Link < ActiveRecord::Base
    has_many :comments, :as => :commentable
end
Paperclip
This is a popular gem for handling uploaded files to your app. Here’s the
documentation on Paperclip:
https://github.com/thoughtbot/paperclip

If you are using Heroku to host your Paperclip app, be sure to look over here:
https://devcenter.heroku.com/articles/paperclip-s3
https://devcenter.heroku.com/articles/config-vars

RAILS WITH AJAX
  Getting started with AJAX
  I think the important thing to know about AJAX is that it’s a way of using javascript and
jQuery to render partials rather than reloading the whole page, or loading a new view
entirely. Here’s some resources that will hopefully help you along the way:

Treehouse: http://teamtreehouse.com/library/ajax-basics/ajax-concepts/introducing-ajax

RailsCast:
http://railscasts.com/episodes/136-jquery-ajax-revised

YouTube:
https://www.youtube.com/watch?v=n6eE-nd3ci4

If you’d like to use Capybara testing with AJAX, be sure to check out PhantomJS and Poltergeist:

http://phantomjs.org/
https://github.com/teampoltergeist/poltergeist

DatabaseCleaner is effective with overcoming the problem with threading and database transactions:
https://github.com/DatabaseCleaner/database_cleaner#rspec-example

Factory Girl: Is a library for setting up Ruby objects as test data. In otherwords, if you’d like to create a user object so you don’t have to repeat yourself in your tests, this tool is for you! (Helpful for creating other objects too - it’s not limited to just creating a user).
https://github.com/thoughtbot/factory_girl_rails

To install, run: $ gem install factory_girl
Add to your Gemfile: gem ‘factory_girl_rails”
Run: $ bundle install
Remember to restart your server
Create a file called “factories.rb” in your spec folder

  Here’s an example of how you might use Factory Girl:

  FactoryGirl.define do
      factory(:user) do
          username('Jane')
          email('Jane@doe.com')
          password('password123')
          password_confirmation('password123')
      end
  end


  If you have authentication on your users, this will help you create a test users with
minimal snags:

FactoryGirl.define do
    factory :user do |user|
       sequence(:email) { |n| "user#{n}@factory.com" }
        user.password{ "supersecretpassword" }
   end
end

Emails
Rails has a built-in system for sending emails called Action Mailer. Here’s the Railscast video on the subject: http://railscasts.com/episodes/61-sending-email-revised

You can use the letter_opener gem to see the emails pop up on a web page:
https://github.com/ryanb/letter_opener

To send actual emails, Mailgun was recommended to us:
http://www.mailgun.com/
Here’s Heroku instructions for setting up Mailgun:
https://devcenter.heroku.com/articles/mailgun

Here’s a helpful blog post on the subject of sending emails from the Model, rather than the Controller (a better practice):
http://www.robbyonrails.com/articles/2009/11/16/sending-email-controllers-versus-models

Pagination
Kaminari is a recommended paginator for Rails 3 and 4 - check it out:
https://github.com/amatsuda/kaminari

