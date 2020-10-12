package com.company;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Text: ");
        String get_text = input.nextLine();
        get_text = (get_text + " ");
        float count_letters = 0;
        float count_words = 0;
        float count_sentences = 0;

        for (int i = 0; i < get_text.length(); i++) {
            if (Character.isLetter(get_text.charAt(i))) {
                count_letters++;
            }
        }

        for (int j = 0; j < get_text.length(); j++) {
            if (get_text.charAt(j) == ' ') {
                count_words++;
            }
        }

        for (int k = 0; k < get_text.length(); k++) {
            String test_text = "";
            test_text = "" + get_text.charAt(k);
            if (test_text.equals(".") || test_text.equals("?") || test_text.equals("!")) {
                count_sentences++;
            }
        }

        float l = (count_letters/count_words)*100;
        float s = (count_sentences/count_words)*100;
        float index = 0.0588f * l - 0.296f * s - 15.8f ;

        if(index < 1){
            System.out.println("Before Grade 1");
        }
        else if(index >= 16){
            System.out.println("Grade 16+");
        }
        else {
            System.out.println("Grade " + Math.round(index));
        }
    }
}
