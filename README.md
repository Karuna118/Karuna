#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    int num;
    printf("Enter number of Employees : ");
    scanf("%d", &num);

    char Emp_Name[num][100];
    char Emp_Job[num][100];
    int Emp_Exp[num];

    for (int i = 0; i < num; i++) {
        printf("Enter Employee %d Name : ", i+1);
        scanf("%s", Emp_Name[i]);
        printf("Enter Employee %d Job Role : ", i+1);
        scanf("%s", Emp_Job[i]);
        printf("Enter Employee %d Experience : ", i+1);
        scanf("%d", &Emp_Exp[i]);
    }

    printf("Total Number of Employees: %d\n", num);
    printf("Employees : ");
    for (int i = 0; i < num; i++) {
        printf("%s ", Emp_Name[i]);
    }
    printf("\n");

    printf("Job Roles : ");
    for (int i = 0; i < num; i++) {
        printf("%s ", Emp_Job[i]);
    }
    printf("\n");

    printf("Experience: ");
    for (int i = 0; i < num; i++) {
        printf("%d ", Emp_Exp[i]);
    }
    printf("\n");

    char specifiedJob[100];
    int n;
    printf("Enter the specific job role to display employees: ");
    scanf("%s", specifiedJob);
    printf("Enter the number of employees you want for a specific job role: ");
    scanf("%d", &n);

    int count = 0; // Count the number of employees with the specified job role
    printf("Employees with the specified job role '%s':\n", specifiedJob);
    printf("Employee_ID\tName\tRole\tExperience\n");
    for (int i = 0; i < num; i++) {
        if (strcmp(Emp_Job[i], specifiedJob) == 0) {
            printf("%d\t%s\t%s\t%d\n", i+1, Emp_Name[i], Emp_Job[i], Emp_Exp[i]);
            count++;
            if (count == n) {
                break;
            }
        }
    }

    if (count == 0) {
        printf("No employees found with the specified job role '%s'.\n", specifiedJob);
    }

    return 0;
}
