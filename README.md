# assignment_data_modeling
Mmmmm.... dataaaaa....

*Include your ERM modeling "pseudocode" in the space below*

Leo and Mike

1. System Goal(s)
  To have student users to be able to access different courses and the lessons that belong to the courses.

Entities
  Courses
  Lessons
  Users
  Join Table

Attributes/Type
  Courses: Title(string), Description(text)
  Lessons: Title(string), Body Text(text), Foreign Key - Course(integer)
  Users: First_name(string), Last_name(string), Email(string), Username(string)
  Join Table: Course ID(integer), User ID(integer)

Relationships
  Course has many lessons
  Lesson has one course
  User has many courses
  Course has many users

2. System Goal(s)
  To allow the user to access their profile and also display any information about themselves.

Entities
  Users
  Profiles
  Locations

Attributes/Type
  Users: Username(string), Email(string)
  Profiles: Age(integer), Gender(string), Foreign Key - Location(integer), Foreign Key - User(integer)
  Locations: City(string), State(string), Country(string)

Relationships
  Users : Profiles - One to one (User owns profile)
  Location: Profiles - One to many

3. System Goal(s)
  Allow users to post links, comments on the links, and/or comments on comments.

Entities
  Users
  Post Links
  Comments

Attributes/Types
  Users: Username(string), Email(string)
  Post Links: Link(string), User Foreign Key(integer)
  Comments: Comment(text), Post Link Foreign Key(integer), Comment Foreign Key(integer), User Foreign Key(integer)

Relationships
  Users : Posts - One to many
  Users : Comments - One to many
  Posts : Comments - One to many
  Comments : Comments - One to many

  4.  System Goal(s)
        Allow users to make orders that are composed of products and keep track of shipments. Each order should be recorded in a user's history.

      Entities/Attributes/Types

        Users: Username(string), email(string)
        Orders: User foreign key
        Shipments: Order foreign key, expected date(dateTime)
        Products: description(string)
        Orders/Products Join Table

     Relationships

       Order:Shipment - One to One (order owns shipment)
       User:Order - One to Many
       Order:Products - Many to Many

     Bonus: If a user deletes their account, their order information remains in the database if they reactivate. If it is decided to delete the linked information, the orders associated with the deleted user's ID would be deleted and the corresponding entries in the shipments and Orders/Products join table would also be deleted.


     4.  System Goal(s)

           To be able to collect data on visitors and users, including things like link clicks, page views, and time on page. This information should also be tied to a given user.

         Entities/Attributes/Types

           Visitors: IP Address(string?)
           Users: Email(string), Username(string), Password(string), Visitor Foreign Key
           Pages: URL(string), Content(text)
           Links: Target URL(string), Text(string)
           Page/Visitor Join Table: Time on page, Page views
           Link/Visitor Join Table: Link clicks
           Pages/Links Join Table

        Relationships
          Visitors:Users - One to one (User belongs to visitor)
          Pages:Links - Many to many
          Visitors:Pages - Many to many
          Visitors:Links - Many to many