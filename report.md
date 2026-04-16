**TutorsTable**

The tutor's table would have the tutor's name, the subjects they tutor, times they are available entered in military time and separated by a comma (Separated by hour intervals for hour long tutoring sessions, 0700, 0800, 0900, 1000), and two primary keys; One that works as the unique tutoring ID and the other unique ID's for the subjects they are tutoring. This tables purpose would be the primary table in deciding tutor assignment. 

**StudentsTable**

The student's table would have the student's name, then student ID that would work as the primary key. This table would hold the simple purpose of cataloguing all students so that when they decide to book an appointment, they can individually be identified by the algorithm.

**AppointmentsTable**

The appointments table would have the timeslot, a foreign ID section for the tutors available during the time slot, and a foreign ID section for the student ID's that have booked said timeslot. This would work as the primary table for correlating students and tutors to an allotted time slot.

In this scenario, the client would be a booking interface that students could access. In this Booking interface, a set of available times and dates for tutors would be available, allowing the student to freely pick any times and dates shown as available. After picking and confirming the time and date of the tutoring session, the interface would then show the user a confirmation of their tutoring date, time, and the tutor that would be assisting them at that timeslot and date. On the server's end, the server would be responsible for appropriating the correct times and dates to the appropriate tutor, then serving said information in the confirmation. Additionally, the server would be responsible for refreshing available timeslots frequently, so that any timeslots that were taken could be hidden from users and prevent double booking. Ultimately, the server's primary job would be to ensure that booking is appropriately handled by allowing forthe incoming data (Booked Appointments) to be transmitted through the server, do the aforementioned tasks, and notify the tutor of their new appointment.

FUNCTION SearchforTutor(subject)
    SET subject = "Calculus I"
    return subject

    WHILE subject != "Calculus I"
        DISPLAY "This Course Does Not Exist or is Not Currently Supported, Please Enter the Following: Calculus I"
        get subject
    ENDWHILE
    IF subject ==  "Calculus I"
        DISPLAY "Current Tutors for this Course Are: Marissa (001553), Johnathan (001554), Enoch (001555)"
ENDIF
ENDFUNCTION

FUNCTION BookAppointment(time,studentID,tutorID)

SELECT tutorID
FROM TutorsTable
    WHILE tutorID != 001553 or 001554 or 001555
        DISPLAY DISPLAY "This is Not a Valid TutorID - Please Enter a Valid Tutor ID"
        get tutorID
    IF tutorID == 001553 
        DISPLAY "You Have Selected Marissa"
    ELSEIF tutorID == 001554
        DISPLAY "You Have Selected Johnathan"
    ELSEIF tutorID == 001555
        DISPLAY "You Have Selected Enoch"
    ENDIF
    
    SELECT studentID
    FROM StudentsTable
    IF studentID != StudentsTable
        DISPLAY "This is Not a Valid Student ID - Please Enter a Valid Student ID"
    ENDIF

    SELECT time
    FROM AppointmentsTable
    IF time != AppointmentsTable
        DISPLAY "This is Not an Available or Valid Timeslot"
ENDIF
RETURN appointment

START Tutoring

    DISPLAY "Please Enter the Subject You Requiring Tutoring for (Currently Only Available for Calculus I)
    get subject

    SET subject = CALL SearchforTutor(subject)

    DISPLAY "Please Enter Your StudentID and Time You Wish to Be Tutored Separated by a Comma (IE: 012345,0700)"
    
    SET appointment = CALL BookAppointment(time,studentID,tutorID)

    DISPLAY "Your appointment for" time "with" tutorID "has been assigned. Would you like to accept? (Y/N)"
    get answer

    WHILE answer == Y or N
        DISPLAY "This is Not a Valid Input"
        get subject
    ENDWHILE
    IF answer == Y
        DISPLAY "Your Appointment is Confirmed - Thank You!"
    ELSE IF answer == N
        DISPLAY "Your Appointment Has Been Cancelled"
    ENDIF
END
