## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ANSWER: ActiveRecord is a framework that makes easier to build web applications. It allows us to talk to the database in an object oriented way.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
ANSWER: Some of the methods that we can call on Team are Team.all, Team.find(1), Team.last, Team.first, Team.new_record? The reason why we have access to them is because the class is inheriting from ActiveRecord.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
ANSWER: Team.find(4) or Team.where(id: 4). I guess that when doing the previous method I would get an object Team with the attributes id, name and owner_id where the owner_id corresponds to a certain number in the table Owners so it would do owner = Owner.find(owner_id that I obtained before).

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
ANSWER: I think that in that case you could do Team.find(4).owner

3. What do they allow you to do? 
ANSWER: Not sure what that refers to. Missing question 5 and 6 in my markdown.
7. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
ANSWER: It would be a many-to-many relationship as students have many teacher and teachers have many students so the best solution would be to build a join table to display which student has each teacher.
This is my schema about it:
<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, https://github.com/ondras/wwwsqldesigner/ -->
<!-- Active URL: http://ondras.zarovi.cz/sql/demo/ -->
<sql>
<datatypes db="mysql">
	<group label="Numeric" color="rgb(238,238,170)">
		<type label="Integer" length="0" sql="INTEGER" quote=""/>
	 	<type label="TINYINT" length="0" sql="TINYINT" quote=""/>
	 	<type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
	 	<type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
	 	<type label="INT" length="0" sql="INT" quote=""/>
		<type label="BIGINT" length="0" sql="BIGINT" quote=""/>
		<type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
		<type label="Single precision" length="0" sql="FLOAT" quote=""/>
		<type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
	</group>

	<group label="Character" color="rgb(255,200,200)">
		<type label="Char" length="1" sql="CHAR" quote="'"/>
		<type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
		<type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
		<type label="Binary" length="1" sql="BINARY" quote="'"/>
		<type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
		<type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
	</group>

	<group label="Date &amp; Time" color="rgb(200,255,200)">
		<type label="Date" length="0" sql="DATE" quote="'"/>
		<type label="Time" length="0" sql="TIME" quote="'"/>
		<type label="Datetime" length="0" sql="DATETIME" quote="'"/>
		<type label="Year" length="0" sql="YEAR" quote=""/>
		<type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
	</group>
	
	<group label="Miscellaneous" color="rgb(200,200,255)">
		<type label="ENUM" length="1" sql="ENUM" quote=""/>
		<type label="SET" length="1" sql="SET" quote=""/>
		<type label="Bit" length="0" sql="bit" quote=""/>
	</group>
</datatypes><table x="399" y="52" name="Students">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="first_name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="age" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="last_name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="school" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="403" y="229" name="Teachers">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="first_name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="last_name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="subject" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="level" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="603" y="151" name="StudentsTeachers">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="student_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Students" row="id" />
</row>
<row name="teacher_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Teachers" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>

8. Define foreign key, primary key, and schema.
ANSWER: 
Primary key is the piece of data that make records unique in a table (it's normally the id).
Foreign key is a primary key that lives in another table.
Schema is the most updated status of the different tables and content of them (column and data type).
9. Describe the relationship between a foreign key on one table and a primary key on another table.
ANSWER: 
The foreign key of one table will have the same value as the primary key of the other table that refers to.
10. What are the parts of an HTTP response?
ANSWER: Status code, header and body. I looked it up because my first thought was that the response was the view.
11. Describe some techniques to make our Sinatra code more DRY. Give an example of when you would use these techniques.
ANSWER: One technique is to create a partial to be displayed in new and edit view so we don't have the same code twice of the exact form.

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
ANSWER: 
.all => returns all records of that class
.order(:name) => returns all records ordered by name
.create(attributes) => Creates a new instance of the class and saves it in the database
.find_by(name: "Edilene") => Looks for a record whose name is the indicated
.update_attributes(name: "Dan") => Updates the mentioned attribute and assignes the new value indicated

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
ANSWER:
rake db:create => creates a database
rake db:migrate => adds the migrations to the database
rake db:seed => adds the information on seeds.rb to the database
rake db:reset => I was told that this task does for you the three previous tasks
4. What can you expect from a group as you begin working together? As you continue working together?
ANSWER:
The DTR is important to define expectations and work styles. Communication is very important during all the parts of the project creation.
5. What two columns does `t.timestamps null: false` create in our database?
ANSWER:
created_at and updated_at with the date and time for each one
6. What cURL flag can you use to send a `POST` request?
ANSWER: Using the -d (or --data) flag. I didn't know so I looked it up.
7. What case does JSON (and JavaScript) use for multi-word variables?
ANSWER: They use camel case that starts with a lowercase letter
8. What case does Ruby use for multi-word variables?
ANSWER: Ruby uses snake_case for them.
9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
ANSWER: It would be a one-to-many relationship where a school has many teachers but a teacher works at only one school.
10. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
ANSWER: It only needs the foreign key school_id that would leave in Teachers table.
This is my schema about it:
<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, https://github.com/ondras/wwwsqldesigner/ -->
<!-- Active URL: http://ondras.zarovi.cz/sql/demo/ -->
<sql>
<datatypes db="mysql">
	<group label="Numeric" color="rgb(238,238,170)">
		<type label="Integer" length="0" sql="INTEGER" quote=""/>
	 	<type label="TINYINT" length="0" sql="TINYINT" quote=""/>
	 	<type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
	 	<type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
	 	<type label="INT" length="0" sql="INT" quote=""/>
		<type label="BIGINT" length="0" sql="BIGINT" quote=""/>
		<type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
		<type label="Single precision" length="0" sql="FLOAT" quote=""/>
		<type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
	</group>

	<group label="Character" color="rgb(255,200,200)">
		<type label="Char" length="1" sql="CHAR" quote="'"/>
		<type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
		<type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
		<type label="Binary" length="1" sql="BINARY" quote="'"/>
		<type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
		<type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
	</group>

	<group label="Date &amp; Time" color="rgb(200,255,200)">
		<type label="Date" length="0" sql="DATE" quote="'"/>
		<type label="Time" length="0" sql="TIME" quote="'"/>
		<type label="Datetime" length="0" sql="DATETIME" quote="'"/>
		<type label="Year" length="0" sql="YEAR" quote=""/>
		<type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
	</group>
	
	<group label="Miscellaneous" color="rgb(200,200,255)">
		<type label="ENUM" length="1" sql="ENUM" quote=""/>
		<type label="SET" length="1" sql="SET" quote=""/>
		<type label="Bit" length="0" sql="bit" quote=""/>
	</group>
</datatypes><table x="201" y="52" name="Schools">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="location" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="401" y="50" name="Teachers">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="first_name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="last_name" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="subject" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="level" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="school_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Schools" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>

11. Give an example of when you might want to store information besides ids on a join table.
ANSWER: When the primary key of the other tables is other than the id.
12. Describe and diagram the relationship between patients and doctors.
ANSWER: It would be a many-to_many relationship, same case and diagrama type than teachers and students.
13. Describe and diagram the relationship between museums and original_paintings.
ANSWER: It would be a one-to_many relationship where a museum has many original_paintings but an original painting only belongs to one museum. So OriginalPaintings table would include the foreign key museum_id. Same case and diagram type than schools and teachers.
14. What are some examples of acceptable values for the parts of an HTTP response?
Some acceptable acceptable values for headers are: Accept: text/plain, Accept-Charset: utf-8, Accept-Encoding: gzip, deflate, Accept-Language: en-CA. I looked it up, I didn't know the answer at all.
15. What types of output do we want to test when we test our controllers?
ANSWER: We can test for example that a specific view is rendered for a certain route.
16. What could you see in your code that would make you think you might want to create a partial?
ANSWER: That the same code is repeated in two views, for example form new and form edit.
17. Why might you use a helper method?
ANSWER: Helper methods are useful to have shorter but still specific code. They are especially useful when the path is long and complex.
