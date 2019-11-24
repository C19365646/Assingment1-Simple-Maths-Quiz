# Assingment1-Simple-Maths-Quiz
Simple Maths Quiz
/* Assignment1.c - A program that was developed to display the main menu of a simple mathematics quiz, then the user inputs the numbers 1 to 4 to anitiate different aspects of the quiz, 1 = how many questions does the user want with a maximum being 5, 2 = starting the quiz and giving random multiplication questions, 3 = giving the results of each round and telling the user whether or not they passed, 4 = ending the quiz
    Author - Michael Hunter
    Student Number - C19365646
    Date of completion - 8-11-19
    Compiler - Borland
    Operating System - Windows 10
*/
#include <stdio.h>
#include <stdlib.h>
int main (void)
{//beginning of int main
    int i;
    int response;
    int input=5;
    int correctAnswers = 0;
    int incorrectAnswers = 0;
    int answer = 0;
    int a;
    int b;
    int ab;
   
    
    do
    {//beginning of do loop
        printf("\nSimple Math Quiz\n");
        printf("Main Menu\n");
        printf("1. How many questions would you like this round.\n");
        printf("2. Start quiz.\n");
        printf("3. Display the amount of questions that were (i) correctly and (ii).\n");
        printf("4. End program.\n");
                
        response= 0; 
                
        printf(" Please enter an option from the main menu: ");
        scanf("%d", &response);
        flushall();
        
        if (response == 1)
        {//beginning of if statement 1
            correctAnswers = incorrectAnswers = 0;
            printf("Please enter # of problems you would wish to try:");
            scanf("%d", &input);
            flushall();
        }//end of if statement 1
                
        if (response == 2)	 
        {//beginning of if statement 2
                    
            for(i = 0; i < input; i++)
            {//beginning of for loop
                a=b=rand() % 10;
                ab=a*b;
                printf("\n%d * %d = ",a ,b);
                scanf("%d", &answer);
                flushall();
                    if((a * b) == answer)
                    {//beginning of if statement 3
                        printf("\nCongratulations You are correct!\n");
                        correctAnswers++;
                    }//end of if statement 3
                    else
                    {//beginning of else statement 1
                        printf("\nThe correct answer is %d\n", ab);
                        incorrectAnswers++;
                    }//end of else statement 1
                            
            }//end of for loop
                    
        }//end of if statement 2
				
        if (response == 3) 
        {//beginning of if statement 4
            printf("\n\nYour Results:\n\n\n");
            printf("Number Incorrect: %d\n", incorrectAnswers);
            printf("Number Correct: %d\n", correctAnswers);
                        
                if(correctAnswers >= incorrectAnswers)
                {//beginning of if statement 5
                    printf("You Passed!\nGood work!\n\n");
                }//end of if statement 5
                else
                {//beginning of else statement 2
                    printf("You did not pass!\nYou need more work!\n\n");
                }//end of else statement 2
                
        }//end of if statement 4
				
        if (response == 4)
        {//beginning of if statement 6
            printf("\nThanks for playing!\n");
        }//end of if statement 6
    
    }//end of do loop
    
    while (response != 4 );
    
    flushall();
    return 0;
}//end of int main
