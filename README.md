# Microverse-Challenge-Answers
### QUESTION 1
***A simple html login page using html, css and js***
```
<!DOCTYPE html>
<html>
  <head>
    <title>Login Page</title>
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <form>
      <label for="username">Username:</label>
      <input type="text" id="username" name="username"><br><br>
      <label for="password">Password:</label>
      <input type="password" id="password" name="password"><br><br>
      <input type="submit" value="Submit">
    </form>
    <script>
      function validateForm() {
        var username = document.forms[0]["username"].value;
        var password = document.forms[0]["password"].value;
        if (username == "" || password == "") {
          alert("Username and password must be filled out");
          return false;
        }
      }
      document.forms[0].addEventListener("submit", function(event) {
        event.preventDefault();
        validateForm();
      });
    </script>
  </body>
</html>
```
***style.css***
```
body {
  background-color: #f2f2f2;
  font-family: Arial, sans-serif;
}

form {
  margin: 0 auto;
  max-width: 400px;
  padding: 20px;
  background-color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

label {
  display: block;
  margin-bottom: 10px;
  font-weight: bold;
}

input[type="text"], input[type="password"] {
  display: block;
  width: 100%;
  padding: 10px;
  border: none;
  border-radius: 3px;
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.1) inset;
  margin-bottom: 20px;
}

input[type="submit"] {
  background-color: #4CAF50;
  color: #fff;
  border: none;
  border-radius: 3px;
  padding: 10px 20px;
  cursor: pointer;
  transition: background-color 0.3s;
}

input[type="submit"]:hover {
  background-color: #3e8e41;
}

```

This code creates a simple login form using HTML, CSS, and JavaScript. When the user submits the form, the `validateForm()` function is called to ensure that both the username and password fields are filled out. If either field is empty, an alert is displayed and the form is not submitted.

### QUETSION 2
***How to scrape a webpage in python***

```
import requests
from bs4 import BeautifulSoup

url = 'https://www.example.com'
response = requests.get(url)

soup = BeautifulSoup(response.text, 'html.parser')

links = soup.find_all('a')
for link in links:
    print(link.get('href'))
```

This code uses the `requests` library to make a request to a website, and the `BeautifulSoup` library to parse the HTML of the page. You can then use the `BeautifulSoup` object to extract the relevant information you need. In this example, we're getting all the links on the page and printing them out. Note that you'll need to install both `requests` and `beautifulsoup4` using pip before you can run this code.

### QUESTION 3
***How to scrape a webpage in node.js***
```
const axios = require('axios');
const cheerio = require('cheerio');

const url = 'https://www.example.com';
axios.get(url)
  .then(response => {
    const $ = cheerio.load(response.data);

    $('a').each((i, link) => {
      console.log($(link).attr('href'));
    });
  })
  .catch(error => {
    console.error(error);
  });

```
This code uses the `axios` library to make a request to a website, and the `cheerio` library to parse the HTML of the page. You can then use the `Cheerio` object to extract the relevant information you need. In this example, we're getting all the links on the page and printing them out. Note that you'll need to install both `axios` and `cheerio` using npm before you can run this code.

### QUESTION 4
***How to create a navigation bar and login***
```
<!DOCTYPE html>
<html>
  <head>
    <title>Navigation Bar and Login</title>
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
    <section>
      <h2>Login</h2>
      <form>
        <label for="username">Username:</label>
        <input type="text" id="username" name="username"><br><br>
        <label for="password">Password:</label>
        <input type="password" id="password" name="password"><br><br>
        <input type="submit" value="Submit">
      </form>
    </section>
  </body>
</html>

```
***style.css***
```
nav {
  background-color: #333;
  overflow: hidden;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

nav li {
  float: left;
}

nav li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav li a:hover {
  background-color: #111;
}

section {
  margin: 50px;
}

h2 {
  font-size: 32px;
  text-align: center;
}

form {
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

label {
  font-size: 24px;
  margin-bottom: 10px;
}

input[type="text"],
input[type="password"] {
  padding: 10px;
  font-size: 18px;
  border: none;
  border-bottom: 2px solid #ccc;
  margin-bottom: 20px;
  width: 100%;
  box-sizing: border-box;
}

input[type="submit"] {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 18px;
}

input[type="submit"]:hover {
  background-color: #45a049;
}

```
This code creates a simple navigation bar and login form using HTML and CSS. The navigation bar is created using an unordered list and styled with CSS. The login form is created using a `form` element, and includes a `label` and `input` element for both the username and password fields. Note that you'll need to style the page using a separate CSS file (referenced in the head element) to get the desired look and feel.

### QUESTION 5
***How to create a footer page with bootstrap***
```
<!DOCTYPE html>
<html>
  <head>
    <title>Footer with Bootstrap</title>
    <link rel="stylesheet" type="text/css" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
  </head>
  <body>
    <div class="container">
      <h1>Page content goes here</h1>
    </div>

    <footer class="bg-dark text-light py-3">
      <div class="container">
        <p>&copy; 2023 Company Name</p>
      </div>
    </footer>

    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.3/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
  </body>
</html>

```
This code creates a simple page with a footer using the Bootstrap framework. The `container` class is used to center the content on the page. The `footer` element has a dark background and light text, and includes a container to center the text. The page also includes the necessary CSS and JavaScript files to use Bootstrap, which are loaded from CDNs. Note that you'll need to customize the content of the page and footer to match your specific requirements.

### QUESTION 6 
***How to Create Zip files with node.js***
```
const fs = require('fs');
const archiver = require('archiver');

const output = fs.createWriteStream('example.zip');
const archive = archiver('zip', {
  zlib: { level: 9 } 
});

output.on('close', () => {
  console.log(`Zip archive created: ${archive.pointer()} total bytes`);
});

archive.on('error', (err) => {
  throw err;
});

archive.file('file1.txt', { name: 'file1.txt' });
archive.file('file2.txt', { name: 'file2.txt' });

archive.pipe(output);
archive.finalize();
```
This code creates a new Zip archive using the archiver module in `Node.js`. The `fs` module is used to create a write stream to the output file, and the archiver module is used to create the actual archive. Two files (file1.txt and file2.txt) are added to the archive using the `archive.file()` method. The output write stream is piped to the archive object, and the `finalize()` method is called to write the zip file to disk. Once the archive is complete, the close event is fired and the total size of the archive is logged to the console.

### QUESTION 7
***How to create a calculator in python***
```
def add(x, y):
    """Addition"""
    return x + y

def subtract(x, y):
    """Subtraction"""
    return x - y

def multiply(x, y):
    """Multiplication"""
    return x * y

def divide(x, y):
    """Division"""
    if y == 0:
        raise ValueError('Cannot divide by zero!')
    return x / y

while True:
    print('Select operation:')
    print('1. Add')
    print('2. Subtract')
    print('3. Multiply')
    print('4. Divide')
    choice = input('Enter choice (1/2/3/4): ')

    if choice not in ('1', '2', '3', '4'):
        print('Invalid input')
        continue

    num1 = float(input('Enter first number: '))
    num2 = float(input('Enter second number: '))

    if choice == '1':
        print(num1, '+', num2, '=', add(num1, num2))

    elif choice == '2':
        print(num1, '-', num2, '=', subtract(num1, num2))

    elif choice == '3':
        print(num1, '*', num2, '=', multiply(num1, num2))

    elif choice == '4':
        try:
            print(num1, '/', num2, '=', divide(num1, num2))
        except ValueError as e:
            print(str(e))
    
    another_calculation = input('Do you want to perform another calculation? (y/n): ')
    if another_calculation.lower() != 'y':
        break

```
This code defines four functions (`add()`, `subtract()`, `multiply()`, and `divide()`) that perform basic arithmetic operations. It then prompts the user to enter two numbers and select an operation to perform using a simple text-based menu. The result of the calculation is then displayed to the user. If the user attempts to divide by zero, a `ValueError` is raised and caught to avoid crashing the program. Finally, the user is prompted to perform another calculation or exit the program.
