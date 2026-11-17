# Hospital Appointment Scheduler

**Project by:** Ayush Raj  
**Course:** B.Tech CSE - First Semester  
**Problem Statement No.:** 74

## About the project

Hospital Appointment Scheduler is a Python console program for a clinic receptionist. It can book, view, reschedule and cancel patient appointments.

The program has two doctors: **Dr. Mehta** and **Dr. Rao**. It stores appointment details in a Python dictionary and gives every successful booking a new appointment ID starting from `A101`.

## Features

- Book an appointment using the patient's name, doctor, date and time.
- View all appointments and the total number of appointments.
- Reschedule an existing appointment.
- Cancel an appointment using its appointment ID.
- Validate calendar dates and time formats using Python's `datetime` module.
- Allow 30-minute slots from `09:00` to `16:30`, inclusive.
- Prevent two appointments for the same doctor at the same date and time.

## Requirements

- Python 3
- No external Python packages are required.

## How to run

1. Open the project folder in Visual Studio Code.
2. Open Terminal > New Terminal.
3. Run `python one.py`.
4. Select an option from the menu. Select option `5` to exit.

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

The selected time must be between `09:00` and `16:30`, and its minutes must be `00` or `30`.

## Test cases

The four test cases and their seven terminal captures are listed in [Summary.md](Summary.md). The screenshot filenames and their order are documented in [screenshots/README.md](screenshots/README.md).

The demonstrated sequence shows:
- A101: Ravi Sharma, Dr. Mehta, 15-11-2026 at 10:00.
- A102: Sita Devi, Dr. Mehta, 15-11-2026 at 16:30.
- A duplicate attempt for Dr. Mehta at 10:00 is rejected.
- The invalid date 31-11-2026 is rejected.
- A101 is rescheduled to 16-11-2026 at 11:30.
- A102 is cancelled; the final view shows only A101 and a total of 1 appointment.

## Limitation

Appointments are stored in a dictionary in program memory. They are cleared when the program closes; permanent file or database storage is not currently implemented.
