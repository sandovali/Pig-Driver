# Pig-Driver


import java.util.Scanner;

public class PigsLab
{
    private boolean player1turn = true;
    
    private boolean player2turn;
    
    private int dieScorePlayer1;
    
    private int dieScorePlayer2;
    
    private int rollScorePlayer1 = 0;
    
    private int rollScorePlayer2 = 0;
    
    private int gameScorePlayer1 = 0;
    
    private int gameScorePlayer2 = 0;
    
    private int continueRollingPlayer1 = 1;
    
    private int continueRollingPlayer2 = 3;
    
    private int playAgain;
    
    
    
   
    
    private String player1name;
    
    private String player2name;
    
    private String name1;
    
    private String name2;
    
    private int headsOrTails;
    
    private int chooseCoin;
    
    public PigsLab ()
    {
    rollScorePlayer1 = 0;
    
    rollScorePlayer2 = 0;
    
    gameScorePlayer1 = 0;
    
    gameScorePlayer2 = 0;
    
    continueRollingPlayer1 = 1;
    
    continueRollingPlayer2 = 3;
    }
    
    public void Play()
    {
      Scanner s = new Scanner( System.in);
    
    System.out.println("Welcome to the best game in the WORLD! This program allows two humans to play the game Pig.\n Each turn, a player repeatedly rolls a die until either a 1 is rolled or the player decides to hold :If the player rolls a 1, they score nothing and it becomes the next player's turn.\n If the player rolls any other number, it is added to their turn total and the player's turn continues.\n If a player chooses to hold, their turn total is added to their score, and it becomes the next player's turn.The first player to score 100 or more points wins.");
    
   
    
    System.out.println("Put your name: ");
    
    name1 = s.nextLine();
    
    System.out.println("Insert the other player's name: ");
    
    name2 = s.nextLine();
    
    headsOrTails = (int) (Math.random() * 2) + 1;
    
    System.out.println(" A coin flip will decide who goes first, good luck: " + name1 + " input 1 to choose heads or input 2 to choose tails");
    
    chooseCoin = s.nextInt();
    
    if ( chooseCoin == headsOrTails)
    {
      player1name = name1;
      
      player2name = name2;
      
      System.out.println( name1 + " you won the coin toss! You will roll first!");
    }
    else
    {
      player1name = name2;
      
      player2name = name1;
      
      System.out.println( name2 + " you won the coin toss! You will roll first!");
    }
    
    System.out.println(" Input any number to begin playing the game ");
    
    int anyNumber = s.nextInt();
    
    
    while ( continueRollingPlayer1 == 1 || continueRollingPlayer2 == 3)
    {  
    System.out.println("Do you want to roll " + player1name + "? If not input 1 if yes input 3");
     
    
    
    continueRollingPlayer1 = s.nextInt();
    
    do 
    {
      dieScorePlayer1 = (int) (Math.random() * 6) + 1;
      
      rollScorePlayer1 += dieScorePlayer1;
      
      System.out.println( player1name + " your roll was: " + dieScorePlayer1);
      
      if (dieScorePlayer1 == 1)
      {
        continueRollingPlayer1 = 1;
        
        rollScorePlayer1 = 0;
        
        System.out.println(" Oh no! You rolled a one! You have lost your turn points!");
      }
      
      else
      {
        System.out.println(player1name + " your current turn score is: " + rollScorePlayer1);
      
      System.out.println("Do you want to continue rolling " + player1name + "? If not input 1 if yes input 3");
      
      dieScorePlayer1 = 0;
    
      continueRollingPlayer1 = s.nextInt();
      }
      
    
    
    if (continueRollingPlayer1 == 1)
    {
      player2turn = true;
      
      player1turn = false;
      
      gameScorePlayer1 += rollScorePlayer1;
      
     
     
      System.out.println(player1name + " your current Score is: " + gameScorePlayer1);
      System.out.println(" The game score is: " + player1name + " (" + gameScorePlayer1 + ")" + " - " + player2name + " (" + gameScorePlayer2 + ")");
      
      rollScorePlayer1 = 0;
      
      dieScorePlayer1 = 0;
      
      
      
    }
    } while (continueRollingPlayer1 == 3);
   
  
  System.out.println("Do you want to roll " + player2name + "? If not input 3 if yes input 1");
     
    
    
    continueRollingPlayer2 = s.nextInt();
    
    do 
    {
      dieScorePlayer2 = (int) (Math.random() * 6) + 1;
      
      rollScorePlayer2 += dieScorePlayer2;
      
      System.out.println(player2name + " your roll was: " + dieScorePlayer2);
      
      if (dieScorePlayer2 == 1)
      {
        continueRollingPlayer2 = 3;
        
        rollScorePlayer2 = 0;
        
        System.out.println(" Oh no! You rolled a one! You have lost your turn points!");
      }
      
      else
      {
        System.out.println(player2name + " your current turn score is: " + rollScorePlayer2);
      
      System.out.println("Do you want to continue rolling " + player2name + "? If not input 3 if yes input 1");
      
      
    
      continueRollingPlayer2 = s.nextInt();
      }
      
    
    
    if (continueRollingPlayer2 == 3)
    {
      player1turn = true;
      
      player2turn = false;
      
      gameScorePlayer2 += rollScorePlayer2;
      
      System.out.println(player2name + " your current Score is: " + gameScorePlayer2);
      System.out.println(" The game score is: " + player1name + " (" + gameScorePlayer1 + ")" + " - " + player2name + " (" + gameScorePlayer2 + ")");
      
       rollScorePlayer2 = 0;
      
      dieScorePlayer2 = 0;
      
      if ( gameScorePlayer1 > 100 && gameScorePlayer1 > gameScorePlayer2 )
      {
        System.out.println("Congratulations " + player1name + " you have won the game!");
        System.out.println("The final score is: " + player1name + " (" + gameScorePlayer1 + ")" + " - " + player2name + " (" + gameScorePlayer2 + ")");
        System.out.println(" Do you want to play again? Press 1 to play again, Press 2 to end session.");

playAgain = s.nextInt();

        if ( playAgain == 1 )
{
  continueRollingPlayer1 = 1;
  
  continueRollingPlayer2 = 3;
  
  gameScorePlayer1 = 0;
  
  gameScorePlayer2 = 0;
}

else
{
  

        continueRollingPlayer1 = 3;
        
        continueRollingPlayer2 = 7;
      }
      }
      
      else if ( gameScorePlayer2 > 100 && gameScorePlayer2 > gameScorePlayer1 )
      {
        System.out.println("Congratulations " + player2name + " you have won the game!");
        System.out.println("The final score is: " + player1name + " (" + gameScorePlayer1 + ")" + " - " + player2name + " (" + gameScorePlayer2 + ")");
        System.out.println(" Do you want to play again? Press 1 to play again, Press 2 to end session.");

playAgain = s.nextInt();

if ( playAgain == 1 )
{
  continueRollingPlayer1 = 1;
  
  continueRollingPlayer2 = 3;
  
  gameScorePlayer1 = 0;
  
  gameScorePlayer2 = 0;
}

else
{
  

        continueRollingPlayer1 = 3;
        
        continueRollingPlayer2 = 7;
      }
}
    }
  } while (continueRollingPlayer2 == 1);
  
  
  } 
    }
}

________________________________
public class PigsFinal
{
  public static void main(String[] args)
  {
    PigsLab pigs = new PigsLab();
   
    pigs.Play();
    
  }
  
}
