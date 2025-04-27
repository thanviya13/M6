# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

int main() {
    float length, width;

    float *ptrLength = &length, *ptrWidth = &width;

    printf("Enter the length of the rectangle: ");
    scanf("%f", ptrLength); 
    printf("Enter the width of the rectangle: ");
    scanf("%f", ptrWidth); 

    float area = (*ptrLength) * (*ptrWidth);

    printf("The area of the rectangle is: %.2f\n", area);

    return 0;
}
```
## OUTPUT
		       	
![img1](https://github.com/user-attachments/assets/e9c9e933-8a8f-43b6-bea4-2b09e6ae083d)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) { 
        printf("Memory allocation failed.\n");
        return 1;
    }

    sprintf(str, "WELCOME"); 

    printf("The string is: %s\n", str);

    free(str);

    return 0; 
}
```
## OUTPUT

![img2](https://github.com/user-attachments/assets/f1ed6878-bea6-4235-8899-fc5e2857673d)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM

```c
#include <stdio.h>

struct Student {
    char name[50];
    int roll_number;
    float marks;
};

int main() {
    struct Student s;

    printf("Enter student's name: ");
    scanf("%s", s.name);
    printf("Enter roll number: ");
    scanf("%d", &s.roll_number);
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll_number);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/4a8f0422-ee1c-401f-99ab-321793067091)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM

```c
#include <stdio.h>

struct Employee {
    char name[50];
    int id;
    float basic_salary, hra, da, gross_salary;
};

int main() {
    struct Employee employees[3];

    for (int i = 0; i < 3; i++) {
        printf("Enter details for Employee %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", employees[i].name);
        printf("ID: ");
        scanf("%d", &employees[i].id);
        printf("Basic Salary: ");
        scanf("%f", &employees[i].basic_salary);
        employees[i].hra = 0.2f * employees[i].basic_salary;
        employees[i].da = 0.8f * employees[i].basic_salary;
        employees[i].gross_salary = employees[i].basic_salary + employees[i].hra + employees[i].da;
    }

    printf("\nEmployee Details:\n");
    for (int i = 0; i < 3; i++) {
        printf("Name: %s, ID: %d, Basic Salary: %.2f, Gross Salary: %.2f\n",
               employees[i].name, employees[i].id, employees[i].basic_salary, employees[i].gross_salary);
    }

    return 0;
}
```
 ## OUTPUT
 ![image](https://github.com/user-attachments/assets/12fca252-6e16-45c9-83d0-6b3d3b1cd275)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM

```c
#include <stdio.h>

struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
};

int main() {
    struct student s[2];
    int i, j;

    for (i = 0; i < 2; i++) {
        printf("Enter 5 subject marks for Student %d:\n", i + 1);
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
    }

    for (i = 0; i < 2; i++) {
        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
    }

    for (i = 0; i < 2; i++) {
        printf("Total marks for Student %d: %d\n", i + 1, s[i].total);
        printf("Average marks for Student %d: %.2f\n", i + 1, s[i].total / 5.0);
    }

    return 0;
}
```
## OUTPUT

 ![img5](https://github.com/user-attachments/assets/abe4dadc-5a45-4f36-9e1a-39cebfa019a5)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


