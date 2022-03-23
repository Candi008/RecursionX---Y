# RecursionX---Y
package challenge5;

import java.util.Scanner;

/**
 *version 1.0 3/23/2022
 * @author 5576564
 * This program asks the user for a word and then replaces any instances of the letter x with a letter y recursively
 */
public class Challenge5 {

    /**
     * @param args the command line arguments
     * 
     */
    //this method asks the user to input a word that is initialized in a variable and then gets sent to the changeXY method
    public static void main(String[] args) {
        // TODO code application logic here
         Scanner keyboard = new Scanner(System.in);
        String repeat = "yes";
        String before = "";
        do
        {
            System.out.println("What is your word you'd like to replace every x with a y?");
            before = keyboard.nextLine();
            System.out.println("Before recursion: " + before);
            String after = changeXY(before);
            System.out.println("After recursion: " +after);
            System.out.println("Would you like to try another word?");
            repeat = keyboard.nextLine();
        }
        while(repeat.equalsIgnoreCase("yes"));
    }
    //this method changes every instance of the letter x with a letter y recursively
    public static String changeXY(String str)
    {
        if (str.length() == 0)
        {
            return str;
        }
        else if(str.charAt(0) == 'x')
        {
            return 'y' + changeXY(str.substring(1));
        }
        else
        {
            return str.charAt(0) + changeXY(str.substring(1));
        }
    }
}
