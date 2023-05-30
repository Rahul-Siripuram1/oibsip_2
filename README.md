# oibsip_2

//NUMBER GUESSING GAME (NGG)
import java.util.Scanner;
import java.util.Random;

class NGGmain{
    public static void main(String args[]){
        Random random=new Random();
        Scanner input=new Scanner(System.in);
        int numOfAtt = 1;
        int numOfGuess;
        int score = 0;
        int originalNumber = random.nextInt(100);
        System.out.println("|**** WELCOME TO NUMBER GUESSING GAME ****| \n");
        System.out.println("You have only 10 attempts to guess the number!\n");
        System.out.println("Rules for scoring:\n");
        System.out.println("1.For every unsuccessful attempt your score will get deducted by -1 point\n");
        System.out.println("2.For successful attempt you will get 10 points\n");
        System.out.println("Guess a number between 1 and 100:\n");
        while(true)
        {
            if(input.hasNextInt())
            {
                numOfGuess=input.nextInt();
                if(numOfGuess == originalNumber)
                {
                    score+=10;
                    System.out.println("Congo!! You Won The Game.");
                    System.out.println("Your score is "+score+" and you guessed it in "+numOfAtt+" attempts");
                    break;
                } else if (numOfGuess < originalNumber) {
                    System.out.println("Your guess is too small!!!");
                    System.out.println("Attempts remaining = "+(10 - numOfAtt));
                    score--;
                } else if (numOfGuess > originalNumber) {
                    System.out.println("Your guess is too big!!!");
                    System.out.println("Attempts remaining = "+(10 - numOfAtt));
                    score--;
                }
                if(numOfAtt == 10)
                {
                    System.out.println("Sorry! You have exceeded the maximum number of attempts!");
                    System.out.println("Better Luck Next Time!!");
                    break;
                }
                numOfAtt++;
            }
            else {
                System.out.println("Please enter a valid number!");
                break;
            }
        }
    }
}
