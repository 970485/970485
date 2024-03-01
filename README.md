#include <stdio.h>
#include <string.h>

// Function to generate health report based on user input
void generateHealthReport(char name[], int age, char sex[], float height, float weight,char pastHealthIssues[], char currentSymptoms[], char userSymptoms[]) {
    // Displaying user information
    printf("\n---------------- Health Report for %s ----------------\n", name);
    printf("Age: %d\n", age);
    printf("Sex: %s\n", sex);
    printf("Height: %.2f meters\n", height);
    printf("Weight: %.2f kilograms\n", weight);
    printf("Past Health Issues: %s\n", pastHealthIssues);


    // List of diseases and their symptoms
    char commonCold[] = "runny nose|sneezing|cough";
    char flu[] = "fever|body aches|fatigue";
    char cancer[] = "unexplained weight loss|persistent cough|fatigue";

    // Checking symptoms and suggesting possible diseases
    if (strstr(commonCold, userSymptoms) != NULL) 
    {
        printf("\nDiagnosis: Common Cold\n");
        printf("Suggested remedies: Rest, stay hydrated, over-the-counter cold medicine.\n");
    } else if (strstr(flu, userSymptoms) != NULL) 
    {
        printf("\nDiagnosis: Flu\n");
        printf("Suggested remedies: Rest, stay hydrated, over-the-counter flu medicine.\n");
    } else if (strstr(cancer, userSymptoms) != NULL) 
    {
        printf("\nDiagnosis: Possible Cancer\n");
        printf("Please consult a healthcare professional for further evaluation.\n");
    } else {
        printf("\nDiagnosis: No common diseases found.\n");
        printf("Please consult a healthcare professional for accurate diagnosis.\n");
    }
}

int main() {
    // Variables to store user information
    char name[50];
    int age;
    char sex[10];
    float height, weight;

    // Variables to store health information
    char pastHealthIssues[200];
    char currentSymptoms[200];

    // Getting user details
    printf("Enter your name: ");
    scanf("%s", &name);

    printf("Enter your age: ");
    scanf("%d", &age);

    printf("Enter your sex (male/female): ");
    scanf("%s", &sex);

    printf("Enter your height (in meters): ");
    scanf("%f", &height);

    printf("Enter your weight (in kilograms): ");
    scanf("%f", &weight);

    // Getting health information
    printf("Enter your past health issues (if any): ");
    scanf("%s", &pastHealthIssues);


    // Presenting common symptoms and taking user input
    char commonSymptoms[] = "cough|fever|fatigue|runny nose|sneezing|body aches";
    printf("Common symptoms: %s\n", commonSymptoms);
    printf("Please input your most relatable symptoms (separated by '|'): ");

    char userSymptoms[200];
    scanf("%s", userSymptoms);

    // Generating and displaying health report
    generateHealthReport(name, age, sex, height, weight, pastHealthIssues, currentSymptoms, userSymptoms);

    // Providing overall remarks to the user
    printf("\nThank you, %s, for using our health program.\n", name);
    printf("Please consult a healthcare professional for personalized advice.\n");
    printf("--------------------------------------------------------\n");
    printf("if you want be healthy and for better experience you have to use our website (Fitness Virtual Reality)");
    return 0;
}

