import java.util.Random;import random
import java.util.Scanner;

public class NumberGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int lowerBound = 1;
        int upperBound = 100;
        int maxAttempts = 10;
        int score = 0;

        System.out.println("Welcome to the Number Game!");
        System.out.println("I'm thinking of a number between " + lowerBound + " and " + upperBound);

        boolean playAgain = true;
        while (playAgain) {
            int targetNumber = random.nextInt(upperBound - lowerBound + 1) + lowerBound;
            int attempts = 0;
            boolean guessedCorrectly = false;

            System.out.println("Can you guess the number? You have " + maxAttempts + " attempts.");

            while (attempts < maxAttempts) {
                System.out.print("Enter your guess: ");
                int userGuess = scanner.nextInt();
                attempts++;

                if (userGuess == targetNumber) {
                    System.out.println("Congratulations! You guessed the correct number in " + attempts + " attempts.");
                    score++;
                    guessedCorrectly = true;
                    break;
                } else if (userGuess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
            }

            if (!guessedCorrectly) {
                System.out.println("Sorry, you've run out of attempts. The correct number was " + targetNumber);
            }

            System.out.print("Do you want to play again? (yes/no): ");
            String playAgainInput = scanner.next();
            playAgain = playAgainInput.equalsIgnoreCase("yes");
        }

        System.out.println("Your final score: " + score);
        System.out.println("Thanks for playing!");
        scanner.close();
    }
}

def play_number_game():
    print("Welcome to the Number Guessing Game!")
    play_again = True
    score = 0

    while play_again:
        lower_limit = 1
        upper_limit = 100
        target_number = random.randint(lower_limit, upper_limit)
        attempts = 0

        print(f"I'm thinking of a number between {lower_limit} and {upper_limit}.")
        max_attempts = 10  # You can adjust the maximum number of attempts here.

        while True:
            user_guess = input("Enter your guess: ")
            try:
                user_guess = int(user_guess)
            except ValueError:
                print("Please enter a valid number.")
                continue

            attempts += 1

            if user_guess == target_number:
                print(f"Congratulations! You guessed the number {target_number} in {attempts} attempts.")
                score += 1
                break
            elif user_guess < target_number:
                print("Too low! Try again.")
            else:
                print("Too high! Try again.")

            if attempts >= max_attempts:
                print(f"Sorry, you've reached the maximum number of attempts. The number was {target_number}.")
                break

        play_again_input = input("Do you want to play again? (yes/no): ").strip().lower()
        if play_again_input != "yes":
            play_again = False

    p
