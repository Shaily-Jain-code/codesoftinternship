import java.lang.*;
import java.util.*;
public class numberGame
{
	public static void main(String[] args) {
	    
	    Random ram=new Random();
	    int RandomNo=ram.nextInt(100) +1;
	    int tries=0;
	    while (true){
		System.out.println("Enter your guess between 1-100");
		Scanner sc=new Scanner(System.in);
		int playerGuess=sc.nextInt();
		tries++;
		if(playerGuess==RandomNo)
		{
		    System.out.println("correct!! You win");
		    System.out.println("It took you " +tries +"tries");
		    break;
		}
		else if(playerGuess<RandomNo)
		{
		    System.out.println("the number is higher. Guess again");
		}
		else
		{
		    System.out.println("the number is low. Guess again");
		}
	    }
	}
}
