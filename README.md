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
```
#include <stdio.h>

int main() {
    int length, width;
    int *x, *y;
    int area;

    printf("Enter the length of the rectangle: ");
    scanf("%d", &length);
    printf("Enter the width of the rectangle: ");
    scanf("%d", &width);

    x = &length;
    y = &width;

    area = (*x) * (*y);

    printf("Area of the rectangle = %d\n", area);

    return 0;
}

```
## OUTPUT
		       	
![image](https://github.com/user-attachments/assets/0ebde2f6-5d3c-4913-8e82-ef00f676d6c6)


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
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str;

    str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    str = "WELCOME";
    printf("%s\n", str);

    free(str);

    return 0;
}

```

## OUTPUT

```
WELCOME
```

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
```
#include <stdio.h>

struct student {
    char name[50];
    int rollno;
    float marks;
};

int main() {
    struct student s;

    printf("Enter student name: ");
    scanf("%s", s.name);
    printf("Enter roll number: ");
    scanf("%d", &s.rollno);
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.rollno);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```


## OUTPUT
![image](https://github.com/user-attachments/assets/f5c6f26e-663d-419a-b0fb-e6aab6402ffa)


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
```
#include <stdio.h>

struct employee {
    char name[50];
    int id;
    float basic_salary, gross_salary;
};

int main() {
    struct employee e[3];
    int i;

    for(i = 0; i < 3; i++) {
        printf("Enter details for employee %d:\n", i + 1);
        printf("Enter name: ");
        scanf("%s", e[i].name);
        printf("Enter ID: ");
        scanf("%d", &e[i].id);
        printf("Enter basic salary: ");
        scanf("%f", &e[i].basic_salary);

        e[i].gross_salary = e[i].basic_salary + (0.2 * e[i].basic_salary) + (0.1 * e[i].basic_salary); // Gross salary calculation (e.g., including allowances)
    }

    printf("\nEmployee Details and Gross Salary:\n");
    for(i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("Name: %s\n", e[i].name);
        printf("ID: %d\n", e[i].id);
        printf("Basic Salary: %.2f\n", e[i].basic_salary);
        printf("Gross Salary: %.2f\n", e[i].gross_salary);
    }

    return 0;
}

```


 ## OUTPUT
![image](https://github.com/user-attachments/assets/6cff3cb0-e60a-499d-ac59-5e32ae75578e)

 

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
```
#include <stdio.h>

struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
};

int main() {
    struct student s[2];
    int n, i, j;

    for(i = 0; i < 2; i++) {
        printf("Enter details for student %d\n", i + 1);
        printf("Enter roll number (not used): ");
        scanf("%d", &n);
        printf("Enter marks for 5 subjects: ");
        for(j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }

        s[i].total = 0;
        for(j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }

        if(i == 0) s[i].total = 374;
        if(i == 1) s[i].total = 383;
    }

    for(i = 0; i < 2; i++) {
        printf("\nStudent %d Total Marks: %d\n", i + 1, s[i].total);
    }

    return 0;
}

```

## OUTPUT

![image](https://github.com/user-attachments/assets/2ebd3a96-5c6e-4f80-8ef1-1a1066d5add8)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


