# Task1
import java.util.Random;
import java.util.Scanner;
public class NumberGuessingGame{
    public static void main(String args[]){
        Scanner sc = new Scanner(System.in);
        Random random = new Random();
        int lowerBound = 1;
        int upperBound = 100;
        int numberOfAttempts = 5;
        int score =  0;
        System.out.println("Welcome to the Number Guessing Game!");

        do{
            int targetNumber = random.nextInt(upperBound - lowerBound + 1) + lowerBound;
            int attempts = 0;
            boolean guessedCorrectly = false;

            System.out.println("\nI have generated a number between " + lowerBound + " and " + upperBound + ". Can you guess it?");

            while(attempts < numberOfAttempts && !guessedCorrectly){
                System.out.println("Enter your guess:");
                int userGuess = sc.nextInt();
                attempts++;

                if(userGuess == targetNumber){
                    System.out.println("Congratulation! You guessed the correct number in " + attempts + " attempts. ");
                    guessedCorrectly = true;
                    score++;
                } else if (userGuess < targetNumber){
                    System.out.println("Too low! Try again.");
                } else{
                    System.out.println("Too high! Try again.");
                }
            }
            if(!guessedCorrectly){
                System.out.println("Sorry , you've run out of attempts. The correct number was: " + targetNumber);
            }
            System.out.println("Do you want to play again? (yes/no): ");
        } while(sc.next().equalsIgnoreCase("yes"));
             System.out.println("Thanks for playing! Your total score is: + score ");
    }
}
