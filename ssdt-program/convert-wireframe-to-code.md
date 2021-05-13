---
title: Convert a Wireframe to Code
description: 
published: true
date: 2021-05-13T16:24:26.097Z
tags: 
---

# Wireframe to Code

Let's say you want to build a super-simplified version of Google Forms for CS Labor Punch correction. The first step in the process will be creating a paper/digital prototype of the product you have in mind. We start with a prototype because changing a prototype is a lot easier than changing lines of code and logic. 

### First we start with building a Balsamiq wireframe: our prototype. 

The components I will need for a functional form are:
1. Title
2. An input field for entering name 
3. Radio buttons for the type of error
4. A datepicker for punch correction date
5. A time input field for the start and end times of the punch 
6. A submit button 

![45.png](/45.png)

Now that I have my prototype ready and approved by all team members and my supervisors, I am ready to code it. 

**Remember that in SSDT, we follow the MVC (Model, View, Controller) framework to build our applications. It is ususally a good idea to start with the backend logic and then work your way to frontend.**

### Let's start Coding! 

**1. Model**
First, we need to think about the data-related logic of the application. How are we storing the data? How is the application retrieving the data? Is a relational database good choice or no-SQL database? How do we want to structure the data efficiently so that it is easy to work with later? and so on. 

Keeping all of that in mind, for our small app we will have one table in the database that will have the following columns:
- `CharField` for storing names
- `CharField` for storing error type 
- `DateField` for storing correction date 
- Two `TimeField` for storing start and end times. 

The database table will look like this in PHPMyAdmin:

![5.png](/5.png)
**Note that I have added data in the table for demo purposes. However, initially the database will be empty.**

We will access the database using the following code that will be saved in a file inside the `/Models` folder. It is the same logic as described above.  

```
class MissedPunches (baseModel):
    full_name                = CharField(null=False)
    error_type               = CharField(null=False)
    correction_date          = DateField(null=False)
    start_time               = TimeField(null=False)
    end_time                 = TimeField(null=False)

    def __str__(self):
        return str(self.__dict__)
```

**2. View**

Time to create the View using HTML, CSS, Bootstrap, and JavaScript. The View is the client facing side of the application, which should look exactly like the prototype we built in the first step. 

You might be curious why we are working on the View before the Controller. That is becuase Controller is a bridge between the Model and the View. To know what the controller is supposed to do, we should first know what components we have in the view. 

For this example, I will just write the HTML code. However, in real life we would add CSS and Bootstrap effects to make the interface user-friendly and pretty. 

```
<!DOCTYPE html>
	<html>
	 <body>
    	<h1>The form element</h1>
      	<form action="/home" method='post'>
          <div>
            <label for="full-name">Full Name</label><br/>
            <input type="text" id="full-name" name='full-name'>
          </div>
          <div>
  					<p>Type of Error</p>
            <input type='radio' id='missing-punch' name='type-of-error' value='missing-punch'>
            <lable for='missing-punch'> Missing Punch </label><br/>
            <input type='radio' id='missing-end-punch' name='type-of-error' value='missing-end-punch'>
    				<lable for='missing-punch'> Missing End Punch </label><br/>
            <input type='radio' id='extra-punch' name='type-of-error' value='extra-punch'>
            <lable for='missing-punch'> Extra Punch </label><br/>
            <input type='radio' id='correction-to-existing-punch' name='type-of-error' value='correction-to-existing-punch'>
            <lable for='missing-punch'> Correction to existing punch </label><br/><br/>
  			</div>
        <div>
          <label for="correction-date"> Date </input>
          <input type='date' id='correction-date' name='correction-date'><br/><br/>
        </div>
        <div>
          <label for='start-time'> Start Time </label>
          <input type='time' id='start-time' name='start-time'><br/><br/>
        </div>
        <div>
          <label for='start-time'> End Time </label>
          <input type='time' id='end-time' name='end-time'><br/><br/>
        </div>
        <button type='submit'>Submit </button>
		</form>
  </body>
</html>
```

**3. Controller**
In this step we need to form a connection between the Model and the View. So that every time a new form is submitted, the data from the View is fetched and stored in the database. 

**Note that we use [Peewee ORM](http://docs.peewee-orm.com/en/latest/) to accomplish this task.** 

```
@app.route('/home', methods=['POST'])
def store_form_data():
	'''
  This function retireves the form data from frontend and populates the database with the data. 
  '''
  
  # Retrieve all the data from View
  data = request.form
  full_name = data.get("full-name")
  error_type = data.get("type-of-error")
  correction_date = data.get("correction-date")
  start_time = data.get("start_time")
  end_time = data.get("end_time")
  
  # Save the data in database
  MissedPunches.create(full_name = full_name, 
  										 error_type = error_type,
                       correction_date = correction_date, 
                       start_time = start_time, 
                       end_time = end_time)
```

That's it! At this point, the data should be saved in the database.



