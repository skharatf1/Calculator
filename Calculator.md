import java.util.Scanner;
import java.util.Random;
public class MyJavaApp {
    
    public static void greetUser(String userName) {
        String welcomeMessage = "Hello, " + userName + "! Welcome to the math quiz.";
        System.out.println(welcomeMessage);
    }

    public static String chooseOperator(int opNum){
        if (opNum == 1){
            return " - ";
        }
        else if(opNum == 2){
            return " - ";
        }
        else if(opNum == 3){
            return " * ";
        }
        else{
            return " / ";
        }
    }

    public static int calculateAnswer(int n1, int n2, String op) {
        int result = 0;
        if(op == " - "){

            return n1 - n2;
        }
        else if(op == " + "){
            
            return n1 + n2;
        }
        else if(op == " * "){
            
            return n1 * n2;
        }
        else if(op == " / "){
            
            return (int)(n1 / n2);
        }
        else{
            return -1;

        }
        
    }


    public static void printQuestion(int num1, int num2, String op) {
        String question = "What is " + num1 + op + num2 + "?";
        System.out.println(question);
    }

    public static void printResult(String userName, int score){
        String farewellMessage = "Thanks for taking the quiz. " + userName + ". Your score is " + score + " out of 5.";
        System.out.println(farewellMessage);
    }


    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        Random random = new Random();

        int num1 = 0;
        int num2 = 0;
        int opNum = 0;
        String op = "";
        int userAnswer = 0;
        int correctAnswer = 0;
        int score = 0;
        int totalQuestions = 0;

        
        System.out.print("Please enter your name: ");
        String userName = scan.nextLine();

       
        greetUser(userName);

        while (totalQuestions < 5){

            num1 = random.nextInt(10) + 1;
            num2 = random.nextInt(10) + 1;
            opNum = random.nextInt(4) + 1;
            op = chooseOperator(opNum);
            printQuestion(num1,num2,op);
            System.out.print("Ans: ");
            userAnswer = scan.nextInt();
            correctAnswer = calculateAnswer(num1, num2, op);
            
            if (userAnswer == correctAnswer){
                System.out.println("Correct answer.");
                score = score + 1;
            }
            else{
                System.out.println("Oops, that's not right. The correct answer is: " + correctAnswer);
            }
            totalQuestions = totalQuestions + 1;
        }

     
        printResult(userName,score);

    }
}
