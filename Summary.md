# Project Summary - Hospital Appointment Scheduler

**Submitted by:** Ayush Raj  
**ERP:** RU-26-01929

**Course:** B.Tech CSE - First Semester  
**Problem Statement No.:** 74

## 1. Project overview

I made a menu-based Python program for a clinic receptionist. The program has five options: Book Appointment, View All Appointments, Reschedule Appointment, Cancel Appointment and Exit.

I used a dictionary named `appt_list` to keep the appointment records. The appointment ID is the dictionary key. Each value stores the patient's name, doctor's name, date and time. The first appointment ID is `A101`, and the ID increases after every successful booking.

The program has two doctors: Dr. Mehta and Dr. Rao. It accepts dates in DD-MM-YYYY format and times in HH:MM format. Appointment slots are available every 30 minutes from 09:00 to 16:30.

## 2. Python concepts used

| Concept | How I used it |
|---|---|
| Dictionary | To store appointment records using appointment IDs |
| Functions | To separate booking, viewing, rescheduling and cancellation |
| `while` loop | To keep showing the menu until Exit is selected |
| `if-elif-else` | To perform the selected menu operation and check conditions |
| `for` loop | To check existing appointments and display records |
| `datetime` module | To validate dates, times and appointment slots |
| CRUD operations | To create, read, update and delete appointment records |

## 3. Validation and conflict checking

I used `datetime.strptime()` to check the date and time. The program rejects invalid calendar dates, such as 31-11-2026. It also checks the appointment range and allows only minutes `00` or `30`.

Before saving an appointment, the `find_conflict()` function compares the doctor, date and time with existing appointments. If the same doctor already has an appointment at that date and time, the new booking is rejected.

During rescheduling, the current appointment ID is passed as `ignore_id`. This makes the conflict-checking function skip the appointment being rescheduled, while still checking all other appointments.

## 4. Test cases and results

The seven supplied VS Code terminal captures are grouped into four test cases below. The screenshot file names and upload order are listed in [screenshots/README.md](<img width="935" height="467" alt="Screenshot 2026-11-17 140241" src="https://github.com/user-attachments/assets/9bbb5775-60a9-49ba-b387-908ef6c4576f" />
).

### Test Case 1 - Normal booking

**Input:** Select option 1; patient Ravi Sharma; doctor Dr. Mehta; date 15-11-2026; time 10:00.

**Expected and demonstrated result:** The appointment is booked successfully with ID `A101`.

**Screenshot:** <img width="935" height="467" alt="Screenshot 2026-11-17 140241" src="https://github.com/user-attachments/assets/6869ba2e-4575-4b95-9b62-6abbcb0ace3a" />


### Test Case 2 - Boundary time slot

**Input:** Select option 1; patient Sita Devi; doctor Dr. Mehta; date 15-11-2026; time 16:30.

**Expected and demonstrated result:** The appointment is booked successfully with ID `A102`. This shows that the last allowed slot, 16:30, is accepted.

**Screenshot:** <img width="933" height="396" alt="Screenshot 2026-11-17 140259" src="https://github.com/user-attachments/assets/da70a88e-98af-4693-a5a7-e0081d4a0b9e" />


### Test Case 3 - Invalid and duplicate inputs

**3(a) Duplicate slot**

Input: Try to book Anil Kumar with Dr. Mehta on 15-11-2026 at 10:00, when Dr. Mehta already has an appointment at that time.

Result: The program displays a slot unavailable message and does not create another appointment for that doctor and time.

Screenshot: <img width="968" height="393" alt="Screenshot 2026-11-17 140312" src="https://github.com/user-attachments/assets/ffd582ab-cd50-42e0-ae25-586f1078858a" />


**3(b) Invalid calendar date**

Input: Try to book Anil Kumar with Dr. Rao using 31-11-2026 at 10:00.

Result: The program displays an invalid date message because 31 November is not a valid calendar date.

Screenshot: <img width="900" height="390" alt="Screenshot 2026-11-17 140336" src="https://github.com/user-attachments/assets/29afcd03-41a6-4b5b-9117-996805e06220" />


### Test Case 4 - Reschedule, cancel and view appointments

**4(a) Reschedule**

Input: Select option 3; enter appointment ID `A101`; new date 16-11-2026; new time 11:30.

Result: Appointment `A101` is rescheduled to 16-11-2026 at 11:30.

Screenshot: <img width="747" height="370" alt="Screenshot 2026-11-17 140352" src="https://github.com/user-attachments/assets/5047d209-4d14-4f3c-8b6f-f0cab29c96dc" />


**4(b) Cancel**

Input: Select option 4 and enter appointment ID `A102`.

Result: Appointment `A102` is cancelled.

Screenshot: <img width="800" height="261" alt="Screenshot 2026-11-17 140407" src="https://github.com/user-attachments/assets/bf1868bd-32a0-459b-91e0-295f048496d7" />


**4(c) Final view**

Input: Select option 2 to view all appointments, then select option 5 to exit.

Result: Only appointment `A101` remains. The terminal displays `Total appointments: 1`.

Screenshot: <img width="891" height="460" alt="Screenshot 2026-11-17 140430" src="https://github.com/user-attachments/assets/fe3738ac-628c-4032-8946-ec723a45a41f" />


## 5. Difficulties I handled

- **Invalid dates:** A date can have the correct format but still not exist. Using `datetime.strptime()` helps reject such dates.
- **30-minute slots:** I checked both the available time range and whether the minute value is 00 or 30.
- **Double booking:** I compared the selected doctor, date and time against saved appointments.
- **Rescheduling:** I used `ignore_id` so an appointment is not treated as a conflict with itself.

## 6. Limitations and future improvements

The program currently runs in the terminal, supports two doctors and stores records only in memory. Appointment data is lost after the program closes. In the future, I can add a database, a graphical user interface, more doctors and permanent appointment records.

## 7. Conclusion

This project helped me practise dictionaries, functions, loops, conditional statements and date-time validation in Python. I also understood how CRUD operations work in a small appointment-management program.
