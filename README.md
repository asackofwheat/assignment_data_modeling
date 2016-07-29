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




