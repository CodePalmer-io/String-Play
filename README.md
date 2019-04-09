# String-Play
import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

class String_game {
    public void reverseString(String n) {
        int i = n.length() - 1;
        String rString = "";
        for (; i >= 0; i--) {
            rString += n.charAt(i);
        }
        System.out.println("The reverse of the word " + n + " " + rString);
    }

    public void toUpper(String n) {
        System.out.println("Uppercase! " + n.toUpperCase());
    }

    public void tolower(String n) {
        System.out.println("Lowercase! " + n.toLowerCase());
    }

    public void countVowels(String n) {
        char vowels[] = {'a', 'e', 'i', 'o', 'u'};
        int count[] = new int[5];
        for (int i = 0; i <= n.length() - 1; i++) {
            for (int j = 0; j < vowels.length - 1; j++) {
                if (n.charAt(i) == vowels[j]) {
                    count[j]++;
                }
            }
        }
        System.out.println("There are a total of 'a' vowels: " + count[0]);
        System.out.println("There are a total of 'e' vowels: " + count[1]);
        System.out.println("There are a total of 'i' vowels: " + count[2]);
        System.out.println("There are a total of 'o' vowels: " + count[3]);
        System.out.println("There are a total of 'u' vowels: " + count[4]);
    }

    public void countLetters(String n) {
        System.out.println("There are a total of " + n.length() + " characters");

    }

    public void characterCount(String n) {
        HashMap<Character, Integer> occurrenceCount = new HashMap<Character, Integer>();
        char[] strArray = n.toCharArray();
        for (char c : strArray) {
            if (occurrenceCount.containsKey(c))
                occurrenceCount.put(c, occurrenceCount.get(c) + 1);

            else {
                occurrenceCount.put(c, 1);
            }
        }

        for (Map.Entry entry : occurrenceCount.entrySet()) {
            System.out.println(entry.getKey() + " " + entry.getValue());
        }
    }
        public void isPalindrome(String n)
        {
            int beginning = 0;
            int end = n.length()-1;
            int middle = (beginning + end) / 2;
            int i;
            for (i = beginning; i < middle; i++)
            {
                if(n.charAt(beginning) == n.charAt(end)) {
                    beginning++;
                    end--;
                    System.out.println(n + " is a Palindrome!!");
                }
                else {
                    System.out.println(n + " is not a Palindrome!!");
                    break;
                }
            }

        }

        // OR -- Code from GeeksFromGeeks.. It's an interesting method to find Palindrome
        public void palindromeCheck(String n)
        {
            //String reverse = n;
            String reverse = new StringBuffer(n).reverse().toString();
            if (n.equals(reverse))
                System.out.println(n + " is a Palindrome -- GeeksFromGeeks");
            else
                System.out.println(n + " is not a Palindrome -- GeeksFromGeeks");
        }

}

    public class Play_With_String {
        public static void main(String args[]) {
            String_game stringTest = new String_game();
            Scanner user_input = new Scanner(System.in);
            System.out.println("Please enter a word or sentence: ");
            String input = user_input.nextLine();
            stringTest.reverseString(input);
            stringTest.tolower(input);
            stringTest.toUpper(input);
            stringTest.countLetters(input);
            stringTest.countVowels(input);
            stringTest.characterCount(input);
            stringTest.isPalindrome(input);
            //stringTest.palindromeCheck(input);

        }
    }

