# SQL Alchemy excercise

This is using SQLAlchemy to create and use a SQLite database from Python 

## 1. Creating the virtual environment
To create a virtual environment, enter the following into the terminal in Visual Studio

```python3 -m venv .venv```

Then activate the environment:

```.venv\Scripts\Activate.ps1```

## 2. Installing the packages

To install the packages:

```python -m pip install -r requirements.txt```

To check the packages installed:

```python -m pip list```

The packages installed should show sqlalchemy in addition to what has been used previously

## 3. Running the API

To run the API from the terminal:

```uvicorn main:app --reload```

## 4. Tests ran in browser

To test in browser, open:

```http://127.0.0.1:8000/docs```

### Test 1: Valid input:

```{ "code": "PY101",  "title": "Python for APIs",  "lecturer": "Nikos" }```

This should return ```201 Created``` with the new course and an ```id```

### Test 2: Invalid input:

```{  "code": "X",  "title": "No",  "lecturer": "A"}```

This should return ```422``` 

## 5. Tests ran in Postman

### Test 1: Return all courses:

Open postman and create a new request:

```GET http://127.0.0.1:8000/courses```

Once executed, this should return the list of courses

### Test 2: Return course by ID:

Create another request

```GET http://127.0.0.1:8000/courses/1```

This should return one course with ID of 1

### Test 3: Post test with valid data:

Create another request

```POST http://127.0.0.1:8000/courses```

Enter the following details in the body with type raw:

```
{
  "code": "P",
  "title": "No",
  "lecturer": "A"
}
```

This should return a validation error.
