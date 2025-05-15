# Random Number Generator & Guessing Game using JAVA

Welcome to the Random Number Generator game — where Java meets mystery, and numbers hide in plain sight! 🤖✨

Think you're good at guessing? Let's put that to the test.

##  What is it?
A console-based number guessing game made in Java for beginners. The computer generates a number between 1 and 100, and it's your job to guess it! With helpful (and dramatic) hints, of course. 😉

"Oh, you're so far away!"

"You're getting closer! Keep going champ!"

"You guessed it right!" 🎉

## How it works
A random number between 1 and 100 is generated using java.util.Random.

You guess the number in the console.

#### The program gives you hints:

Way off? It tells you you’re so far away! 😢

Close enough? It cheers you on with motivational hints 💪

Exact match? Victory is yours! 🎉


# Take a look at the code !
```
import java.util.*;

public class Main{
    public static int randomNumber(){
        Random random = new Random();
        return random.nextInt(100)+1;
    }
    public static String hint(int num, int guess)
    {
        if(guess == num)
        {
            return "Correct";
        }
        if(guess < (num-5) || guess > (num+5))
        {
            return "Oh, You're so far away\n";
        }
        else{
            return "You're getting closer! Keep going champ!\n";
        }
    }

    public static void runGuess()
    {
        Scanner sc = new Scanner(System.in);
        int num = randomNumber();
        String hint;

        while(true)
        {
            System.out.println("Guess a number between 1 - 100 : ");
            int guess = sc.nextInt();
            hint = hint(num, guess);

            if(hint.equals("Correct"))
            {
                System.out.println("You guessed it right!");
                break;
            }
            else{
                System.out.println(hint);
            }
        }
    }
    public static void main(String[] args)
    {
        runGuess();
    }
}

```
