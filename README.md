# jogo-da-forca-hangman-game
codigo em desenvolvimento sobre um jogo da forca / a code in develop about a hangman game

import java.util.Scanner;
public class jogoDaForca
{   private static char nextGuess(Scanner in)
    {
        char guess;
        String line;
        line = in.nextLine();
        guess = line.charAt(0);
        return guess;
    }
    
    private static void printHeader()
    {
        System.out.println("Jogo da Forca");
        System.out.println("==============");
        System.out.println();
    }
    
    public static void main (String [] args)
    {
        char guess;         
       
        String line;        // a letra que foi digitada
        String segredo;     // a palavra que deve ser adivinhada
        String word;         // as letras que foram adivinhadas
        String wrongs;      //letras tentadas e erradas
        
        printHeader();
        
        segredo = "hangman";
        word = "-------";
        wrongs = "";
        
        Scanner in = new Scanner (System.in);
        
        System.out.printf("Palavra: %s\n", word);
        System.out.printf("Tentativa: ");
        
        line = in.nextLine();
        guess = line.charAt(0);
        
        guess = nextGuess(in);
        
        System.out.println(guess);
        
        if(segredo.contains("" + guess))
        {
            System.out.printf("Tentadas: %s\n", wrongs);
        }
        else
        {
            wrongs = wrongs + guess + " ";
        }
        System.out.printf("Erradas:    %s\n", wrongs);
        
        in.close();
    }
}
