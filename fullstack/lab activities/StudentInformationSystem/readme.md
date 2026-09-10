# BCA124-2OL – Full Stack Development

## LAB 1: AJAX, JavaScript, Methods and Properties

### Project Title

**Student Information System using AJAX**

### Objective

The objective of this lab is to create a simple AJAX program using JavaScript that demonstrates how to:

1. Create an AJAX request object.
2. Initialize a request by setting the URL.
3. Open a connection.
4. Use a callback function to handle the response.
5. Send the request.

### Technologies Used

* HTML
* JavaScript
* AJAX
* XMLHttpRequest

### Project Files

```text
AJAX-Lab-1/
│
├── index.html
├── student.txt
└── README.md
```

### Description

This project demonstrates how AJAX can be used to retrieve student information from a text file without refreshing the entire webpage.

When the user clicks the **"Get Student Details"** button, JavaScript creates an `XMLHttpRequest` object and sends a GET request to `student.txt`.

The response received from the server is then displayed on the webpage.

### AJAX Steps Used

#### 1. Create the AJAX Object

```javascript
var xhr = new XMLHttpRequest();
```

The `XMLHttpRequest` object is used to communicate with the server asynchronously.

#### 2. Set the URL

```javascript
var url = "student.txt";
```

The URL specifies the resource from which the student information is retrieved.

#### 3. Open the Connection

```javascript
xhr.open("GET", url, true);
```

The `open()` method initializes the request.

* `GET` – HTTP request method.
* `url` – The file from which data is requested.
* `true` – Makes the request asynchronous.

#### 4. Use the Callback Function

```javascript
xhr.onreadystatechange = function() {

    if (xhr.readyState == 4 && xhr.status == 200) {
        document.getElementById("studentInfo").innerHTML =
            xhr.responseText;
    }
};
```

The `onreadystatechange` property is used as a callback function. It checks whether the request has completed successfully.

* `readyState == 4` means the request is completed.
* `status == 200` means the request was successful.
* `responseText` contains the data received from the server.

#### 5. Send the Request

```javascript
xhr.send();
```

The `send()` method sends the request to the server.

### Important AJAX Methods and Properties

| Method / Property    | Purpose                                         |
| -------------------- | ----------------------------------------------- |
| `XMLHttpRequest()`   | Creates an AJAX request object                  |
| `open()`             | Initializes the request                         |
| `send()`             | Sends the request                               |
| `onreadystatechange` | Callback function for monitoring request status |
| `readyState`         | Shows the current state of the request          |
| `status`             | Shows the HTTP response status                  |
| `responseText`       | Contains the response received from the server  |

### How to Run the Project

1. Open the project folder in **Visual Studio Code**.
2. Make sure `index.html` and `student.txt` are in the same folder.
3. Install the **Live Server** extension in VS Code if it is not already installed.
4. Right-click `index.html`.
5. Select **Open with Live Server**.
6. The webpage will open in the browser.
7. Click **Get Student Details**.
8. The student information from `student.txt` will be displayed on the webpage.

### Expected Output

Initially, the webpage displays:

```text
Student Information

[ Get Student Details ]
```

After clicking the button:

```text
Student Information

Name: Shon
Course: BCA
Semester: 1
Subject: Full Stack Development
```

### Conclusion

This lab demonstrates the basic working of AJAX using JavaScript and `XMLHttpRequest`. The program retrieves information asynchronously from a text file and displays it on the webpage without requiring a complete page refresh.
