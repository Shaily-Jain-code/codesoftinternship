import java.lang.*;
import java.util.*;
public class studentGradeCalc
{
	public static void main(String[] args) {
	    
	    System.out.println("let's know your result");
	    Scanner sc=new Scanner(System.in);
	    int i,n,sum=0;
	    System.out.println("enter no. of subjects");
	    n=sc.nextInt();
	    int marks[] = new int[n];
	    System.out.println("enter marks of each subject (out of 100)");
	    for(i=0;i<n;i++)
	    {
	        marks[i]=sc.nextInt();
	    }
	    for(i=0;i<n;i++)
	    {
	        sum=sum+marks[i];
	    }
            System.out.println("your total marks are " + sum);
	    float avg = sum/n;
            System.out.println("average percentage is " + avg);
	    if(avg>=0&&avg<33){
	        System.out.println("you are fail!!");
	    }
	    else if(avg>=33&&avg<60){
	        System.out.println("Your grade is D");
	    }
	    else if(avg>=60&&avg<75){
	        System.out.println("Your grade is C");
	    }
	    else if(avg>=75&&avg<85){
	        System.out.println("Your grade is B");
	    }
	    else if(avg>=85&&avg<95){
	        System.out.println("Your grade is A");
	    }
	    else if(avg>=95&&avg<=100){
	        System.out.println("Your grade is A++");
	    }
	    else{
	        System.out.println("invalid marks");
	    }
	}
}
