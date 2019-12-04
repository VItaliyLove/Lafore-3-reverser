# Lafore-3-reverser

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.nio.Buffer;

class Algorithm {
    static class myStack {

        private int maxSize;
        private int top;
        private char[] arr;

        public myStack(int newMaxSize) {
            maxSize = newMaxSize;
            top = -1;
            arr = new char[maxSize];
        }

        public void push(char elem) {
            top++;
            arr[top] = elem;
        }

        public char pop() {
            return arr[top--];
        }

        public int getTop() {
            return top;
        }

        public boolean isEmpty() {
            if (top == -1)
                return true;
            return false;
        }
    }

    static class Reverser {

        private String input;
        private String output;

        public Reverser(String newInput) {
            input = newInput;
        }

        public String doReverse() {
            output = "";
            myStack cont = new myStack(input.length());
            for (int i = 0; i < input.length(); i++)
                cont.push(input.charAt(i));
            while (!cont.isEmpty())
                output += cont.pop();
            return output;
        }
    }

    public static void main(String[] arg) throws IOException {

        System.out.println("Write any word: ");
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
        String word = reader.readLine();
        System.out.println(new Reverser(word).doReverse());

    }

}
