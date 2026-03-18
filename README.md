# college-Dbms-lab-5
# README

## Lab: Data Retrieval using JOINs

### Objective:
Is lab ka objective hai multiple tables se data retrieve karna using INNER JOIN, taaki related information ek saath fetch ki ja sake bina database structure change kiye.

### Tables Used:
- Student (StudentID, Name, DepartmentID)
- Enrollment (StudentID, CourseID, Semester, Grade)
- Course (CourseID, CourseName, Credits, FacultyID)
- Faculty (FacultyID, Name, Designation, DepartmentID)
- Department (DepartmentID, DepartmentName)

### Key Concept: JOIN
JOIN ka use multiple tables ko connect karne ke liye hota hai based on Primary Key aur Foreign Key.

Example:
Student.StudentID = Enrollment.StudentID

### Type of JOIN Used:
- INNER JOIN → Sirf matching records return karta hai

### Lab Tasks:

Part A: Student–Enrollment Relationship
1. Student ID, Name + CourseID
2. Student Name + Semester
3. Student Name + Grade

Part B: Course–Faculty Relationship
4. CourseName + Credits + Faculty Name
5. Courses by FacultyID 'F201'
6. Faculty Name + Designation + CourseName

Part C: Student–Course–Enrollment
7. Student Name + CourseName
8. Student Name + CourseName + Semester
9. Semester 4 records
10. Courses by StudentID 'S401'

Part D: Department-Based JOIN
11. Student Name + DepartmentID + CourseName
12. Department-wise courses
13. Faculty Name + Department Name

Part E: Filtering & Sorting
14. Students from Department 'D101' with CourseName
15. Sorted by Student Name (Ascending)

### Important Points:
- JOIN queries read-only hoti hain (data modify nahi karti)
- Aliases (S, E, C) use karne se query short aur readable hoti hai
- Ek query me multiple JOIN use ho sakte hain

### Example Query:
SELECT S.Name, C.CourseName
FROM Student S
INNER JOIN Enrollment E ON S.StudentID = E.StudentID
INNER JOIN Course C ON E.CourseID = C.CourseID;
