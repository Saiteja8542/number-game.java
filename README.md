import random

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

    print(f"Your final score is {score}.")

if __name__ == "__main__":
    play_number_game()
