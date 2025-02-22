//RockPaperScissor_Game
//Rock Paper Scissor game using C language 
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Function to get the computer's choice
char getComputerChoice() {
    int randNum = rand() % 3;  // Generate a random number between 0 and 2
    if (randNum == 0)
        return 'r'; // Rock
    else if (randNum == 1)
        return 'p'; // Paper
    else
        return 's'; // Scissors
}

// Function to determine the winner
void determineWinner(char user, char computer) {
    printf("Computer chose: %c\n", computer);

    if (user == computer) {
        printf("It's a tie!\n");
    } else if ((user == 'r' && computer == 's') || 
               (user == 'p' && computer == 'r') || 
               (user == 's' && computer == 'p')) {
        printf("You win!\n");
    } else {
        printf("You lose!\n");
    }
}

int main() {
    char userChoice;
    
    // Seed the random number generator
    srand(time(0));

    // Get user input
    printf("Enter your choice (r for Rock, p for Paper, s for Scissors): ");
    scanf(" %c", &userChoice);

    // Validate user input
    if (userChoice != 'r' && userChoice != 'p' && userChoice != 's') {
        printf("Invalid choice! Please enter r, p, or s.\n");
        return 1;
    }

    // Generate computer choice
    char computerChoice = getComputerChoice();

    // Determine the winner
    determineWinner(userChoice, computerChoice);

    return 0;
}
