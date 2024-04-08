# NumberGame

import java.util.Scanner;
import java.util.Random;

public class Main
{
            public static void main(String args[])
            {
                Scanner sc= new Scanner(System.in);
                Random random = new Random(); // for taking random number...

                int minRange= 1;
                int maxRange= 50;
                int attemptLimites= 7; // limit of attempts to guess the number..
                 int score =0;

                 boolean playAgain = true;  // if user want to play again the game..

                 while(playAgain)
                 {
                      int randomNumber= random.nextInt(maxRange-minRange+1)+minRange;//this expression will produce a random number between 1 and 100 ..
                       int attempts =0;
                       boolean guessCorrectly = false; // for  checking whether the guess is correct or not..(taking false for pass the value true = !gusseCorrectly)

                       System.out.println("Wellcome to the Game !..");
                       System.out.println("Select a number betwee "+minRange+" and "+maxRange+"."+ " with the attemps of "+ attemptLimites+".");

                             while(attempts<attemptLimites)
                             {
                                System.out.println("Enter your guess : ");
                                int userGuess= sc.nextInt();
                                attempts++;

                                if(userGuess==randomNumber)
                                {
                                    System.out.println("Congratulations !! you guessed right number.."+ randomNumber+ " in attemps number "+ attempts);
                                    score= score+attempts;
                                    guessCorrectly=true ;
                                    break;

                                }
                                else if(userGuess <randomNumber)
                                {
                                    System.out.println(" your gussed in too low !.. try again..");
                                }
                                else
                                {
                                    System.out.println("Your gussed is too High!... try again..");
                                }
                           }// end of inner while loop ..

                           if(!guessCorrectly)
                           {
                                System.out.println("Sorry ! you can't gussed the number  correctly.... The correct number is = " + randomNumber);
                            }

                            System.out.println("Your Current Score is = "+ score);
                            System.out.println("You want to play again? (yes/no)");
                            String userChoise= sc.next();
                            playAgain = userChoise.equalsIgnoreCase("yes"); //  check if user wants to continue playing or not .

                 }// end of outer while loop ..

                 System.out.println("Thanks for playing!.. Your Final score is : " +score );
               } //end of main method
        }   // end of class Guess



