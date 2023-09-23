# APPOINTMENT BOOKER - appointment booking system

## [Video Demo](https://youtu.be/rGI-LijGCcg)

## Why?

Appointment booker is a 1:1 appointment booking system. Registered users can create booking calendars, where anyone can book appointments with the calendar creator.

This is my final project for the course [CS50's Introduction to Computer Science](https://cs50.harvard.edu/x/2022/).

## Technologies

Appointment booker is built with Python3 and Flask, SQL with sqlite3, HTML with Jinja2 and a little hint of JavaScript. The layout of the website is by Simple CSS, with the colors modified a little. Requirements for extra packages can be found in the requirements.txt file.

## Features

The main features of the booking system are user registration and login, creating booking calendars and sharing them with anyone who can book appointments without registration.

### User registration and login

As a new user registers, the password validity, unique username and e-mail validity are checked in the backend. Login is handled with Flask-Session.

### Creating new booking calendars

A new booking calendar gets an automatically generated ID. The calendar has a title and the creator can also include some additional information that is displayed for the users who book the appointments.

When adding appointments, the calendar creator can define a default duration for an appointment, so they don't need to calculate the duration themselves. Instead, the ending time of the appointment is calculated with JavaScript as the beginning time is inserted. When adding appointments, the backend validates that appointments do not collide with existing appointments.

It is possible to edit the title and additional information of the calendar, and even delete the whole calendar. It is also possible to edit individual appointments (starting and ending time) and delete them.

### Sharing the booking calendar

The calendar creator can share the calendar id number so that users can insert it in the Appointment booker frontpage and access the calendar that way. The calendar creator can also view the booking view of the calendar in the calendar view and share the direct link that way.

### Booking appointments

Booking appointments is possible for anyone and doesn't require login. Calendar id or a direct link to the booking calendar are required in order to access the calendar. User insert their name and e-mail and selects one appointment from the appointment list. When they submit the form, they can see the time frame they booked, the calendar information and contact information for the calendar creator. When an appointment is booked, it will not be shown as available to other users.

### Viewing booked appointments

The calendar creator can see the real-time booking situation when they are logged in. They calendar view displays all the appointments, and for booked appointments, participant name and e-mail link are shown.

## Files

- **app.py** : Contains functionality for the database management as well as the Flask routes for the backend.

- **helpers.py** : Contains functions for user input validation and time formatting and validation

- **templates** folder : contains HTML templates for each route. File layout.html is the basis of the website layout, and the other templates are rendered based on the route and the request.

- **static** folder : contains simple.css file (courtesy of https://simplecss.org/) as well as styles.css file with some additional css styling.

- **database.db** : This is the SQLite database. The database contains four tables: user, calendar, appointment and answer, in hierarchical order. When the server is started, the tables are created according to the **schema.sql** file.

- **requirements.txt** : Lists all the package requirements for the software to run.

## Future of the project

The next steps for improving the project are making sure all data is validated properly and all possible errors are handled accordingly.

New features I would like to add are (for example):

- editing several appointment time frames on the same page
- changing username, password and e-mail
- appointments with several participants
- automatic confirmation e-mails for participants (when they have booked a meeting)
- for a logged-in user: list of booked appointments in other user's calendars, possibility to cancel and change them
- group e-mail from calendar creator to participants.

## Conclusion

This project was the first actual project I have ever created myself. I'm happy I was able to create a draft of something that in the real world would actually be useful. I have learned a lot during this process, especially about how to acquire new skills in order to create new features in my project. I'm looking forward to continuing to improve this project and apply the knowledge I have gained in many new projects in the future.
