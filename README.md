# ADVANCED-ATM-MACHINE
Creating a some advanced atm machine

import java.util.Scanner;
public class ATM {
    float Balance;
   private int pin = 1234;

    void cheakpin() {
        Scanner sc = new Scanner(System.in);
        System.out.println();
        System.out.println("==================  ** Welcome to my Application ** ==================");
        System.out.println();
        System.out.println("Enter Your Pin:");
        int enteredpin = sc.nextInt();
        if (enteredpin == pin) {

            menu();
        } else {
            System.out.println("invalid Pin,Please try again:");
            cheakpin();
        }
    }

    void menu(){
        System.out.println("==========  ** Enter Your Choice **  ==========");
        System.out.println();
        System.out.println(" 1. Cheak A/C Balance ");
        System.out.println();
        System.out.println(" 2. Withdraw Money ");
        System.out.println();
        System.out.println(" 3.Deposit Money ");
        System.out.println();
        System.out.println(" 4.Exit");

        Scanner sc=new Scanner(System.in);
        int opt=sc.nextInt();
        switch (opt) {
            case 1:
                   CheakBalance();
                   break;
            case 2:
                   WithdrawMoney();
                   break;
            case 3:
                   DepositMoney();
                   break;
            case 4:
                   Exit();
                   break;       
            default:
                System.out.println("Enter valid choice");
        }
    }

    void CheakBalance() {
        System.out.println(" Your Balance = " + Balance);
        menu();
    }

    void WithdrawMoney() {
        System.out.println("Enter amount to widthdraw :");
        System.out.println();
        Scanner sc = new Scanner(System.in);
        float amount = sc.nextFloat();
        if (amount > Balance) {
            System.out.println("Insufficent Balance :");
        } else {
            Balance = Balance - amount;
            System.out.println("Withdraw Successful :");
        }
        menu();
    }

    void DepositMoney() {
        System.out.println("Enter amount to deposit :");
        System.out.println();
        Scanner sc = new Scanner(System.in);
        float amount = sc.nextFloat();
        Balance = Balance + amount;
        System.out.println("Deposit Successful :");
        menu();
    }
    void Exit(){
        System.out.println("Thanks for using this application");
        cheakpin();
    }

    public static void main(String args[]) {
        ATM obj = new ATM();
        obj.cheakpin();
    }
}
