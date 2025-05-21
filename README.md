<h1 align="center">Cinema-Booking</h1>

Movie ticket booking web application with MERN stack (MongoDB, Express, React, NodeJS) & Tailwind CSS

Demo: https://cinema-booking-client.vercel.app/

## Table of Contents
* [Project Purpose](#project-purpose)
* [Technologies](#technologies)
* [Guide](#guide)
* [How to run the app](#how-to-run-the-app)

## Project Purpose
The purpose of this project is to improve my full-stack web development skills, learning front-end technologies like React and Tailwind CSS, and backend technologies like Node.js, Express, and MongoDB.

## Technologies
* React v18.2.0
* React Router Dom v6.14.2
* React Hook Form v7.45.4
* Tailwind CSS v3.3.3
* Vite v4.4.8
* NodeJS
* Mongoose v7.4.2
* Express v4.18.2
* MongoDB



## Guide

### 🧩 Role / Feature

There are 3 roles on this website with corresponding permissions:

| Role  | Permisson / Feature |
|-------------|-------------|
|Viewer (Not logged in)  | **1. View released showtimes by choosing from** <br> &emsp;- Movie in home page <br>  &emsp;- Cinema's theater in cinema page <br> &emsp;- Cinema's schedule in schedule page <br> **2. View released showtimes for today and the future** <br> **3. View seats for released showtimes on the showtime page**|
|User   | **1. All Viewer permissions** <br> **2. Purchase tickets on the showtime page** <br> **3. View purchased tickets on the ticket page**|
|Admin   | **1. All User permissions** <br> **2. View all showtimes for any date** <br> **3. Manage cinemas** <br> **4. Manage theaters** <br> &emsp;- View theater's row, column, seats information <br> **5. Manage showtimes** <br> &emsp;- Search & filter & sort showtimes <br> &emsp;- View details of booked seats <br> **6. Manage movies** <br> **7. Manage user & admin**|

### Viewer
Viewer have access to these pages for viewing released showtimes.

<details>
    <summary>Home page</summary><br>

1. Select a movie

2. Select a date by either typing it into the input or selecting from the calendar to view showtimes 

3. Optionally, select a cinema to filter

4. Click on a showtime to view seats

</details>

<details>
    <summary>Cinema page</summary><br>

1. Select a cinema

2. Select a date to view its theaters and showtimes

3. Click on a showtime to view seats
</details>

<details>
    <summary>Schedule page</summary><br>

1. Select a cinema

2. Select a date to view its schedule for each theater

3. Click on a showtime to view seats
</details>

<details>
    <summary>Showtime page</summary><br>

1. View available seats (white boxes) and unavailable seats (gray boxes)

2. Viewer will be redirected to the login page if they click "Purchase"
</details>

### User
User have all viewer permission. Including, the ability to purchase and view their own tickets

<details>
    <summary>Register / Login</summary><br>

1. To create an user account, fill in a username, email, and password, then click "Register"

2. To log in, fill in username and password, then click "Login"

</details>

<details>
    <summary>Showtime page / Purchase tickets</summary><br>

1. Select available seats 


2. Click the "Purchase" button and confirm to purchase tickets

</details>

<details>
    <summary>Ticket page</summary><br>

1. View purchased tickets


</details>

### Admin
Admin have all permission.

<details>
    <summary>Create an admin account</summary><br>

1. Register a new user.
2. Access MongoDB and locate the user's data.
3. Update the user's role to `admin`.
4. The user will now become admin.
   
Note: After obtaining the first admin account, this user can assign admin roles to others using the User page.

</details>
    
<details>
    <summary>Home page</summary><br>

1. Admin can view theater's row, column, seats information.


2. Admin can view all showtimes for any date

</details>

<details>
    <summary>Cinema page</summary><br>


**Add a new cinema**
1. Type the cinema's name.


2. Click the "Add" button


**Edit a cinema's name**
1. Click the "Edit" button

2. Enter the new cinema name and click "Save"


**Delete a cinema**
1. Click the "Delete" button and confirm by clicking "OK"


**Add a theater to the cinema**
1. Fill the letter of the last row and the number of the last column seat, then click "Add"


**Delete the last added theater**
1. Click the "Delete" button at the bottom of the page


**Add showtimes**
1. Select a movie
2. Fill in the following values:
    * **Showtime:** Movie start time
    * **Repeat:** For example, 1 means the showtime is added for today only, while 4  mean the showtime is added for today and the next 3 days.
    * **Release now:** Check to release this showtime for viewers and users to view or book
    
    **Auto increase**
    * **Showtime:** Check to automatically update the showtime value based on the ending time of this showtime, along with a specified gap. This is useful when adding consecutive movies, ensuring appropriate spacing between showtimes.
    * **Date:** Check to enable automatic increase of showtime to the next day if it exceeds 24 hours
    * **Gap:** The minimum duration between movie showtimes
    
    **Rounding**
    * **5-min:** Round up the auto-increased showtime value to the nearest 5 minutes, e.g., 12:21 -> 12:25
    * **10-min:** Round up the auto-increased showtime value to the nearest 10 minutes, e.g., 12:21 -> 12:30

3.  Click the "Add" button

4. The new showtimes will added to the theater. An eye-slash icon indicates that this showtime is not yet released

</details>

<details>
    <summary>Schedule page</summary><br>

</details>


<details>
    <summary>Showtime page</summary><br>

1. View details of booked seats
2. Release, unrelease, or delete the showtime by clicking the button in the top-right corner


</details>

<details>
    <summary>Movie page</summary><br>


**Add a movie**
1. Fill in the movie name, URL of the poster, and the length in hours (optional) and minutes. Then, click "Add" to add the movie.


**Delete a movie**

1. Click the "Delete" button and confirm by clicking "OK"

</details>

<details>
    <summary>Search page</summary><br>

1. Filter & sort showtime and select to release / unreleased / delete them
2. Click a "View" button to view seats

</details>

<details>
    <summary>User page</summary><br>

1. View usernames, email addresses, roles, and tickets of users.
2. Click the "View Tickets" button to see a user's purchased tickets.
3. Click the "Set Admin" or "Set User" button to change the user's role.
4. Click the "Delete" button to delete the account.


</details>

## How to run the app
1. Download the code
2. Create .env file in /server
```
PORT=8080
DATABASE=<your MongoDB connection string URI>
JWT_SECRET=<any random JWT secret>
JWT_EXPIRE=30d
JWT_COOKIE_EXPIRE=30
```
3. Start server side
```
cd server
npm install
npm start
```
4. Start client side
```
cd client
npm install
npm run dev
```
