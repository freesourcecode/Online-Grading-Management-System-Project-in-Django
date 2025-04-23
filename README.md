#  Online Grading Management System Project in Django  with Source Code

The **Online Grading Management System is created based on Python, Django, and SQLITE3 Database**.

The Grading System is a web-based system with the primary purpose of allowing Professors/Teachers to track class grades and access a school’s student list. 

Via their ID number, the student can easily access their grades online.

>[!NOTE]
>  To start creating a Online Grading Management System in Python Django, makes sure that you have PyCharm Professional IDE Installed in your computer.

## Student Features

* Login Page

The page where the system administrator enters their system credentials in order to gain access to the system’s administrative side.

* View Grades

This is the page where the student can view their grades online.

## Faculty Features

* **Login Page**

The page where the system company enters their system credentials in order to gain access to the system’s company side.

* **Add Exam**

This is the page where the faculty can add exam for their student.

* **Set Criteria**

This is the page where the faculty can set a criteria for the grades of student.


## How to Create an Online Grading Management System in Django?

Here are the steps on how to create an **Online Grading Management System in Django** with Source Code.

1. **Open file**.

First, open “pycharm professional” after that click “file” and click “new project”.

![image](https://github.com/user-attachments/assets/7c5a5331-1ace-4158-a26e-60f761b67120)

2. **Choose Django**.

Next, after click “new project”, choose “Django” and click.

3. **Select file location**.

Then, select a file location wherever you want.

4. **Create application name**.

After that, name your application.

5.  **Click create**.

Lastly, finish creating project by clicking “create” button.

![image](https://github.com/user-attachments/assets/1d0d47d9-ee11-4246-9a14-2f5d4746fde9)

6. **Start Coding**.

Finally, we will now start adding functionality to our Django Framework by adding some functional codes.

## Functionality and Codes

* **Create template for the criteria form i**

In this section, we will learn on how create a templates for the criteria form. 

To start with, add the following code in your setcriteria.html under the folder of gms/templates.

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Set Criteria</title>
	{%load staticfiles%}
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"> </script>
	<script src="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"> </script>
	<link href='https://fonts.googleapis.com/css?family=Satisfy' rel='stylesheet' type='text/css'>
	<link rel="stylesheet" type="text/css" href="{% static 'gms/style_setcriteria.css' %}"/>
</head>
<body>
	<nav class="navbar navbar-inverse">
		<div class="container-fluid">
		<!--Header-->
		<div class="navbar-header">
			<button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#topNavBar">
				<span class="icon-bar"></span>
				<span class="icon-bar"></span>
				<span class="icon-bar"></span>
			</button>
			<a class="navbar-brand" href="/authenticated/">Home</a>
		</div>

		<!--items-->
		<div class="collapse navbar-collapse" id="topNavBar">
			<ul class="nav navbar-nav">
				<li class="active">
					<a href="/authenticated/{{course_no}}">{{course.course_name}}</a>
				</li>
			</ul>

			<ul class="nav navbar-nav navbar-right">
				<li class="">
					<a href="/logout/">
						<span class="glyphicon glyphicon-off" aria-hidden="true"></span>&nbsp;
						LogOut
					</a>
				</li>
			</ul>
		</div>
		</div>
	</nav>
	<h3 style="text-align: center;">Enter the lower limit for individual grades for the course {{course}}</h3>
	<hr>
	<div style="width:300px; margin:0 auto;">
		{% if error %}
			<p style="color:red; text-align: center;">Minimum criteria marks should be decreasing order! </p>
		{% endif %}
		<form action="/authenticated/{{course_no}}/setcriteria/" method="post">	
			{% csrf_token %}
			<label>Lower limit for A grade</label>
		    <input type="number" id="grade_a" name="grade_a" value="{{course.a}}" min="{{course.b}}" max="99" required><br>
		    <label>Lower limit for B grade</label>
		    <input type="number" id="grade_b" name="grade_b" value="{{course.b}}" min="{{course.c}}" max="{{course.a}}" required><br>
		    <label>Lower limit for C grade</label>
		    <input type="number" id="grade_c" name="grade_c" value="{{course.c}}" min="{{course.d}}" max="{{course.b}}" required><br>
		    <label>Lower limit for D grade</label>
		    <input type="number" id="grade_d" name="grade_d" value="{{course.d}}" min="0" max="{{course.c}}" required><br>
			
		  	<button class="btn btn-primary" type="submit" style="float: right;width: 100px;" >  Save  </button>
		  	
		</form>
		<a href="/authenticated/{{course_no}}" style="float: left;"  class="btn btn-primary">Go Back</a>
	</div>
</body>
</html>
```

### 📌Here's the full documentation for the [Online Grading Management System Project in Django](https://itsourcecode.com/free-projects/python-projects/online-grading-management-system-project-in-django-with-source-code/)
