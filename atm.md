import java.lang.*;
import java.util.*;
class BankAccount{
    private double balance;
    
    public BankAccount(double initialBalance){
        this.balance=initialBalance;
    }
   
    public double getBalance(){
        return balance;
    }
    
    public void deposit(double amount){
        if(amount>0){
            balance+=amount;
            System.out.println("you have deposited " +amount +"amount and your current balance is : " +balance);
        }
        else{
            System.out.println("invalid amount please enter again...");
        }
    }
    
    public void withdraw(double amount){
        if(amount>0&&amount<=balance){
            balance=balance-amount;
            System.out.println("you have withdrawed " +amount +"rupees and your current balance is : " + balance);
        }
        else{
            System.out.println("invalid amount");
        }
    }
}
class userAccount{
    private BankAccount bankAccount;
    
    public userAccount(BankAccount bankAccount){
        this.bankAccount=bankAccount;
    }
    
    public void menu(){
        System.out.println("ATM menu : ");
        System.out.println("1 : Check Balance ");
        System.out.println("2 : withdraw Money");
        System.out.println("3 : deposit money");
        System.out.println("4 : EXIT");
    }
    
    public void transaction(int choice, Scanner scanner){
        switch(choice){
            case 1:
                System.out.println("Your current balance is : " +bankAccount.getBalance());
                break;
            case 2:
                System.out.println("enter the amount you want to withdraw");
                double withdrawAmount=scanner.nextDouble();
                bankAccount.withdraw(withdrawAmount);
                break;
            case 3:
                System.out.println("enter the amount you want to deposit");
                double depositAmount=scanner.nextDouble();
                bankAccount.deposit(depositAmount);
                break;    
            case 4:
                System.out.println("EXIT");
                break;
            default:
                System.out.println("invalid choice");
        }
    }
}

public class ATM {

    public static void main(String[] args) {
       Scanner scanner = new Scanner(System.in);
       
       System.out.println("enter initial account balance");
       double initialBalance=scanner.nextDouble();
       BankAccount bankAccount = new BankAccount(initialBalance);
       
       userAccount useraccount= new userAccount(bankAccount);
       
       while(true){
           useraccount.menu();
           System.out.println("select an option");
           int choice =scanner.nextInt();
           
           useraccount.transaction(choice, scanner);
       }
    }
    
}
