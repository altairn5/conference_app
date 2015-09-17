Ready for Rails!
This has been a very light introduction to faking data, seeding your database, and working with models and inheritance. We're ready to dive into rails and work with ActiveRecord!

1. Create a new rails application

Make sure you're in a new project folder

rails new conference_app -T -d postgresql
cd conference_app
git init
git add . -A
git commit -m "inital commit, rails skeleton"
subl .
2. Create a Talk model

rails g model talk topic:string duration:integer
git diff # take a look at the files you just created!
And take a look at the following files:

app/models/talk.rb
db/migrate/1234566789_create_talks.rb
3. Setup your database

Download and Launch Postgres.app. You should see an elephant in your menu if it's running.

Next, create your application database:

rake db:create # create a new database on your machine
rake db:migrate # instruct your database what tables it needs to contain
4. Launch the rails console and create your first talk!

rails console
# or
rails c
Confirm that your model exists

Talk
 #=> Talk(id: integer, topic: string, duration: integer, created_at: datetime, updated_at: datetime) 
Create your first record!

Talk.create({topic: "Playing with Models in the Rails Console"})
Talk.count
Talk.all
Try the following:

Create 3 new Talks in the Rails Console.
Delete the last talk you created
Find the first talk
Find the last talk
Search by id
Search by title
Sort by title
Update the title of the last talk you created
Delete all the talks you created.
Pro-Tip: Remember, when you're working in the console/repl up-arrow is your friend! (That and "hanging a dot" + "double-tabbing").

5. Can you seed your database?

Take a look at db/seed.rb.

Add the following line:

p "Hello from seed.rb"
Now run the following from your command line (not the console!):

rake db:seed
# Hello from seed.rb
The seed.rb file is magic, because it already knows about all of the models and gems in your rails app. All you have to do is tell it what data to create!

Can you seed your database with speaker and talks?
