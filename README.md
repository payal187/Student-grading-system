#include <stdio.h>


char calculateGrade(float percentage) {
    if (percentage >= 90) return 'A';
    else if (percentage >= 80) return 'B';
    else if (percentage >= 70) return 'C';
    else if (percentage >= 60) return 'D';
    else return 'F';
}

int main() {
    int n, i;
    printf("Enter number of students: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        char name[50];
        int roll, marks[5], total = 0;
        float percentage;
        char grade;

        printf("\nEnter student %d details:\n", i + 1);
        printf("Name: ");
        scanf(" %[^\n]", name);  
        printf("Roll Number: ");
        scanf("%d", &roll);

        printf("Enter marks in 5 subjects: ");
        for (int j = 0; j < 5; j++) {
            scanf("%d", &marks[j]);
            total += marks[j];
        }

        percentage = total / 5.0;
        grade = calculateGrade(percentage);

        
        printf("\nStudent Details:\n");
        printf("Name: %s\nRoll Number: %d\nTotal Marks: %d\nPercentage: %.2f\nGrade: %c\n",
               name, roll, total, percentage, grade);
    }

    return 0;
}
