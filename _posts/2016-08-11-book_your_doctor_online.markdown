---
layout: post
title:  "Book Your Doctor Online!"
date:   2016-08-11 20:27:55 +0000
---


Ladies and Gentlemen,

This post is about how to create a sinatra web application with complex relationship tables, different user categories and a login process. We will take the example of an application which allows users to book an appointment online with a doctor either by name or by specialty.

We want our app to allow a patient to:
1. book an appointment online with a doctor either by name or by specialty
2. see all his coming appointments
3. modify or cancel any coming appointments
4. see all his historical appointments
5. see all his historical appointments with a specific doctor
6. see and modify his profile

We want our app to allow a doctor to:
1. book an appointment online with an existing or new patient
2. see all his coming appointments
3. modify or cancel any coming appointments
4. see all his historical appointments
5. see all his historical appointments with a specific patient
6. see and modify his profile

**The Database Structure**

We have 3 main tables which are doctors, patients and appointments knowing that a doctor and a patient are somehow related through appointments. However, in order to have a database structure more in line with the reality, relationships are a bit more complex than this and we need to create 2 join tables. We also have one other table which is specialties and which applies only to doctors.

Intuitively, we understand that a patient has many doctors and a doctor has many patientsso clearly there must be a join table beetwen doctors and patients to translate this "many-to-many" relationship. Let's call this join table the doctor_patients table.

Then a doctor_patients relationship can have many appointments (indeed we can imagine that they see each other on monday and then on wednesday of the same week and then in one month from now on) and an appointment can have many doctor_patients relationships. **This is where it might be a bit tricky** but think about the case where in the same city we have doctor 1 and patient 1 who have an appointment on monday at 1.00pm and doctor 2 and patient 2 also have an appointment on monday at 1.00pm. Clearly the object "appointment monday 1.00pm has many doctor_patients relationships. So here **we need to create another join table that we will call meetings and that will join the doctor_patients table with the appointments table.**

We also have a "many-to-many" relationships between doctors and specialties and will create a join table called doctor_specialties to reflect this relationship.

Once we create our database structure we can access doctors, patients, doctor_patients, meetings, and appointments and have all information needed.

**The Models**

Sinatra-activerecord will allow us to access to basic information about doctors, patients, appointments, etc. but given the complexity of the relationships, I would strongly suggest to create appropriate methods for doctors, patients and appointments allowing to easily check for instance if a doctor is available or not, create a new appointments after checking if doctor and patient exist in the database and if the doctor is available, modify or cancel an appointment, listing all the comings appointments a doctor and a patient have and idem for historical appointments, etc.

Besides, it appears that several methods like listing all the comings appointments a doctor and a patient have and idem for historical appointments, ... could be very similar for both a doctor and a patient. In order to have a more concise and better design in our code following the DRY principle, we suggest to write these methods inside a module either as instance or class methods.

**The Login Session**

Pretty straigth forward, we created a login session which is nothing else than a hash stored on a cookie during the session (i.e. until the user either logout or the cache from the browser is cleared). When needed, our controllers route check if the user is logged in or not and display the appropriate web page. We also use the gem bcrypt in order to have a stronger password encryption for security purposes.

**Conclusion**

This sinatra application is a example of a web application with complex relationships between various table and classes. In order to fully understand the code and the explanation above, you can have a look at my repo on github by clicking on the following link: https://github.com/ivanpilot/doctorfinder

If you  have any suggestion or would like any additional information, please feel free to reach out to me at ivanpilot@gmail.com.
