#include <iostream>
#include <cstdlib> // for rand() and srand()
#include <ctime>   // for time()

using namespace std;

int main() {
    srand(static_cast<unsigned int>(time(0))); // Seed for random number generation
    int numberToGuess = rand() % 100 + 1; // Random number between 1 and 100
    int userGuess = 0;
    int attemptCount = 0;
    char playAgain;

    do {
        cout << "Guess a number between 1 and 100: ";
        cin >> userGuess;
        attemptCount++;

        if (userGuess < numberToGuess) {
            cout << "Too low! Try again." << endl;
        } else if (userGuess > numberToGuess) {
            cout << "Too high! Try again." << endl;
        } else {
            cout << "Congratulations! You've guessed the number " << numberToGuess << " in " << attemptCount << " attempts!" << endl;
        }

    } while (userGuess != numberToGuess);

    cout << "Do you want to play again? (y/n): ";
    cin >> playAgain;

    if (playAgain == 'y' || playAgain == 'Y') {
        main(); // Restart the game
    } else {
        cout << "Thank you for playing!" << endl;
    }

    return 0;
}
