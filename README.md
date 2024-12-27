#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void guess_the_number() {
    int number_to_guess, user_guess, attempts = 0;

    // Seed the random number generator with the current time
    srand(time(0));

    // Generate a random number between 1 and 100
    number_to_guess = rand() % 100 + 1;

    printf("Welcome to the Guess the Number game!\n");
    printf("I have selected a number between 1 and 100. 
    Try to guess it.\n");

    // Loop until the user guesses the correct number
    do {
        printf("Enter your guess: ");
        scanf("%d", &user_guess);
        attempts++;

        // Check if the guess is correct
        if (user_guess < number_to_guess) {
            printf("Too low! Try again.\n");
        } else if (user_guess > number_to_guess) {
            printf("Too high! Try again.\n");
        } else {
            printf("Congratulations! You've guessed the number %d in %d 
            attempts.\n", number_to_guess, attempts);
        }
    } while (user_guess != number_to_guess);
}

int main() {
    // Call the guessing game function
    guess_the_number();
    return 0;
}
    
