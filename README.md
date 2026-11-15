# Hospital Appointment Scheduler

Project by: Ayush Raj  
ERP: 01929
Course: B.Tech CSE - First Semester  
Subject: Programming Fundamentals and Logic Building Using Python  
PS No.: 74

## About the project

Hospital Appointment Scheduler is a small Python console program for a clinic receptionist. It can book a patient's appointment, show the saved appointments, reschedule an appointment and cancel an appointment.

The program has two doctors: **Dr. Mehta** and **Dr. Rao**. It stores appointment details in a Python dictionary and gives every new appointment an ID starting from `A101`.

## Features

- Book an appointment by entering the patient's name, doctor, date and time.
- View all appointments and the total number of appointments.
- Reschedule an existing appointment.
- Cancel an appointment using its appointment ID.
- Check the date and time with Python's `datetime` module.
- Allow 30-minute slots from `09:00` to `16:30` (both ends included).
- Stop two appointments from being booked with the same doctor at the same date and time.

## Requirements

- Python 3
- No external Python packages are required.

## How to run

1. Download or clone this repository.
2. Open the project folder in a terminal or in a Python editor.
3. Run `python one.py`.
4. Select an option from the menu and enter the requested details.
5. Select option `5` to close the program.

## Menu

| Option | Work |
|---|---|
| 1 | Book Appointment |
| 2 | View All Appointments |
| 3 | Reschedule Appointment |
| 4 | Cancel Appointment |
| 5 | Exit |

## Input format

- Date: `DD-MM-YYYY` (example: `15-11-2026`)
- Time: `HH:MM` in 24-hour format (example: `10:00`)
- Doctors: `Dr. Mehta` or `Dr. Rao`

A valid appointment time must be between `09:00` and `16:30`, and its minutes must be either `00` or `30`.

## Project files

```text
hospital-appointment-scheduler/
├── one.py
├── README.md
├── Summary.md
└── screenshots/
    ├── test_case_1_and_2.png
    ├── test_case_3.png
    └── test_case_4.png
```

## Test cases

The test screenshots are available in the `screenshots` folder. The test run starts with an empty appointment dictionary, so the first two successful bookings receive IDs `A101` and `A102`.

## Note

The appointments are stored in memory while the program is running. They are cleared when the program is closed. File or database storage is not part of the given minimum requirements.
