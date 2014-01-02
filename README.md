MathGame
==========

import java.util.*;
import java.awt.*;


public class MathGame
{
  public static final int POINTS = 0;
  public static final Scanner CONSOLE = new Scanner(System.in);
  public static final Random RANDOM = new Random();
  public static final int WIDTH = 600;
  public static final int HEIGHT = 600;
  
  
  public static void main( String[] args)
  {
    System.out.println();
    System.out.println("Hello! Welcome to the Math Game created by Matthew Frierson. Please enjoy!");
    System.out.println();
    System.out.println("Directions: There are 5 levels that contain math equations to solve.");
    System.out.println("If you answer an equation correctly you get a point or lose a point if incorrect.");
    System.out.println("If your answer is not a number and it is not an integer. You will have to respond again."); 
    System.out.println("Get four points to advance to the next level, except for level five where"); 
    System.out.println("you need eight points.");
    System.out.println("If on level one you get to -3 points, it will be game over and the program will end.");
    System.out.println("Careful, you might even get moved down a level. When you get to 24 points you get a surprise");
    System.out.println("Good Luck!!\n\n");
   
    levelOne(POINTS);
 
  }
 
  public static void levelOne(int POINTS)
  {
    System.out.println("\t\t LEVEL ONE \n\n");  
    
    System.out.println("In this level, there will be addition equations to solve.");
    System.out.println("Do not use decimal points in your answers.");
    System.out.println("Type the answer you think is correct in the blank and press enter to submit answer.\n\n");
    
    
    int levelOneMax = 100;
    int levelOneMin = 0;
    
    while( POINTS <= 3 && POINTS >= -2)
    {
    
    int randomValue1 = RANDOM.nextInt (levelOneMax - levelOneMin + 1) + levelOneMin;
    int randomValue2 = RANDOM.nextInt (levelOneMax - levelOneMin + 1) + levelOneMin;
    
    System.out.println( randomValue1 + " + " + randomValue2 + " = ? " );
    
    int answer = checkUserInput();
    
    
      
       if( answer == randomValue1 + randomValue2)
       {
         System.out.println("Correct");
         POINTS++;
       }
    
       else if( answer != randomValue1 + randomValue2)
       {
         System.out.println("Incorrect");
         POINTS--;
      
       }
       
       System.out.println("You have " + POINTS + " point(s)\n\n");
    
    }
    
    
    if( POINTS == 4 )
    {
      levelTwo(POINTS);
    }
    else if( POINTS == -3 )
    {
      System.out.println("GAME OVER");
      
    }
  
    
    
  }
 
  public static void levelTwo(int POINTS)
  {
    System.out.println("\t\t LEVEL TWO\n\n" );
    
    System.out.println("In this level, there will be subtraction equations to solve.");
    System.out.println("Do not use decimal points in your answers.");
    System.out.println("Type the answer you think is correct in the blank and press enter to submit answer.\n\n");
    System.out.println("To enter a negative number, press the hyphen key and then the number.");
    
    int levelTwoMax = 100;
    int levelTwoMin = 0;
    
    while( POINTS <= 7 && POINTS >= 4 )
    {
    
    int randomValue1 = RANDOM.nextInt (levelTwoMax - levelTwoMin + 1) + levelTwoMin;
    int randomValue2 = RANDOM.nextInt (levelTwoMax - levelTwoMin + 1) + levelTwoMin;
    
    System.out.println( randomValue1 + " - " + randomValue2 + " = ? " );
    
    int answer = checkUserInput();
    
    
      
       if( answer == randomValue1 - randomValue2)
       {
         System.out.println("Correct");
         POINTS++;
       }
    
       else if( answer != randomValue1 - randomValue2)
       {
         System.out.println("Incorrect");
         POINTS--;
      
       }
       
       System.out.println("You have " + POINTS + " point(s)\n\n");
       
       
    }
    
     if(POINTS == 3)
       {
         levelOne(POINTS);
       }
     else if(POINTS == 8)
     {
       levelThree(POINTS);
     }
   
  }
  
  public static void levelThree(int POINTS)
  {
    System.out.println("\t\t LEVEL THREE\n\n" );
    
    System.out.println("In this level, there will be multiplication equations to solve.");
    System.out.println("Do not use decimal points in your answers.");
    System.out.println("Type the answer you think is correct in the blank and press enter to submit answer.\n\n");
    
    
    int levelThreeMax = 100;
    int levelThreeMin = 0;
    
    while( POINTS <= 11 && POINTS >= 8)
    {
    
    int randomValue1 = RANDOM.nextInt (levelThreeMax - levelThreeMin + 1) + levelThreeMin;
    int randomValue2 = RANDOM.nextInt (levelThreeMax - levelThreeMin + 1) + levelThreeMin;
    
    System.out.println( randomValue1 + " * " + randomValue2 + " = ? " );
    
      int answer = checkUserInput();
    
    
      
       if( answer == randomValue1 * randomValue2)
       {
         System.out.println("Correct");
         POINTS++;
       }
    
       else if( answer != randomValue1 * randomValue2)
       {
         System.out.println("Incorrect");
         POINTS--;
      
       }
       
       System.out.println("You have " + POINTS + " point(s)\n\n");
        
    
    }
    
    if(POINTS == 7)
       {
         levelTwo(POINTS);
       }
     else if(POINTS == 12)
     {
       levelFour(POINTS);
     }
    
  }
  
 
  public static void levelFour(int POINTS)
  {
    System.out.println("\t\t LEVEL FOUR\n\n" );
    
    System.out.println("In this level, there will be division equations to solve.");
    System.out.println("Do not use decimal points in your answers.");
    System.out.println("Type the answer you think is correct in the blank and press enter to submit answer.\n\n");
    System.out.println("To type the correct answer, put it in whole numbers with out the remainder.");
    System.out.println("For example: 19/5 the correct answer would be 3 without the remainder of 4.");
    
    
    while( POINTS <= 15 && POINTS >= 12)
    {
    
    int randomValue1 = RANDOM.nextInt (300 - 10 + 1) + 10;
    int randomValue2 = RANDOM.nextInt (10 - 1 + 1) + 1;
    
    System.out.println( randomValue1 + " / " + randomValue2 + " = ? " );
    
    int answer = checkUserInput();
    
    
      
       if( answer == randomValue1 / randomValue2)
       {
         System.out.println("Correct");
         POINTS++;
       }
    
       else if( answer != randomValue1 / randomValue2)
       {
         System.out.println("Incorrect");
         POINTS--;
      
       }
       
       System.out.println("You have " + POINTS + " point(s)\n\n");
       
    }
    
    if(POINTS == 11)
       {
         levelThree(POINTS);
       }
     else if(POINTS == 16)
     {
       levelFive(POINTS);
     }
    
  }
  
  public static void levelFive(int POINTS)
  {
    System.out.println("\t\t LEVEL FIVE\n\n" );
    int levelFiveMax = 100;
    int levelFiveMin = 0;
    
   
    
    String[] operator = new String[4];
    
    operator[0] = " + ";
    operator[1] = " - ";
    operator[2] = " * ";
    operator[3] = " / ";
    
    
    while( POINTS <= 23 && POINTS >= 16)
    {
    
    int randomValue1 = RANDOM.nextInt (levelFiveMax - levelFiveMin + 1) + levelFiveMin;
    int randomValue2 = RANDOM.nextInt (levelFiveMax - levelFiveMin + 1) + levelFiveMin;
    
    int operatorChooser = RANDOM.nextInt (3 - 0 + 1 ) + 0;
    
    String mathOperator = operator[operatorChooser];
    
      if( mathOperator == " + " )
      {
        System.out.println( randomValue1 + mathOperator + randomValue2 + " = ? " );
    
        int answer = checkUserInput();
        
        
        if( answer == randomValue1 + randomValue2)
        {
          System.out.println("Correct");
          POINTS++;
        }
    
        else if( answer != randomValue1 + randomValue2)
        {
          System.out.println("Incorrect");
          POINTS--;
      
        }
       
      }
       
       if( mathOperator == " - " )
      {
         
         System.out.println( randomValue1 + mathOperator + randomValue2 + " = ? " );
    
         int answer = checkUserInput();
       
         
        if( answer == randomValue1 - randomValue2)
        {
          System.out.println("Correct");
          POINTS++;
        }
    
        else if( answer != randomValue1 - randomValue2)
        {
          System.out.println("Incorrect");
          POINTS--;
      
        }
       
      }
       
       if( mathOperator == " * " )
      {
         System.out.println( randomValue1 + mathOperator + randomValue2 + " = ? " );
    
         int answer = checkUserInput();
         
        if( answer == randomValue1 * randomValue2)
        {
          System.out.println("Correct");
          POINTS++;
        }
    
        else if( answer != randomValue1 * randomValue2)
        {
          System.out.println("Incorrect");
          POINTS--;
      
        }
       
      }
       
       if( mathOperator == " / " )
      {
         
         int randomValue3 = RANDOM.nextInt (300 - 10 + 1) + 10;
         int randomValue4 = RANDOM.nextInt (10 - 1 + 1) + 1;
         
         System.out.println( randomValue3 + mathOperator + randomValue4 + " = ? " );
    
         int answer = checkUserInput();
         
         
         
         
        if( answer == randomValue3 / randomValue4)
        {
          System.out.println("Correct");
          POINTS++;
        }
    
        else if( answer != randomValue3 / randomValue4)
        {
          System.out.println("Incorrect");
          POINTS--;
      
        }
       
      }
      
       System.out.println("You have " + POINTS + " point(s)\n\n");
    }
    
    if(POINTS == 15)
       {
         levelFour(POINTS);
       }
    else if(POINTS == 24)
    {
      DrawingPanel dp = new DrawingPanel(WIDTH, HEIGHT);
      congratulations(dp);
    }
  }
  
  public static void congratulations( DrawingPanel dp )
  {
    
    Graphics g = dp.getGraphics();
    
    g.setColor(Color.GREEN);
    g.fillOval(30,200,70,70);
    g.setColor(Color.ORANGE);
    g.fillOval(30,300,70,70);
    g.setColor(Color.CYAN);
    g.fillOval(30,400,70,70);
    g.setColor(Color.MAGENTA);
    g.fillOval(30,500,70,70);
    
    
    Color a = new Color(0,255,255);
    g.setColor( a );
    g.fillOval(500,200,70,70);
    Color b = new Color(186, 85,211);
    g.setColor( b );
    g.fillOval(500,300,70,70);
    Color c = new Color(240,230,140);
    g.setColor( c );
    g.fillOval(500,400,70,70);
    Color d = new Color(173,255,47);
    g.setColor( d );
    g.fillOval(500,500,70,70);
    
    g.setColor(Color.YELLOW);
    g.fillOval(150,230,300,300);
    
    g.setColor(Color.BLACK);
    g.fillOval(230,290,40,40);
    g.fillOval(330,290,40,40);
    
    g.setColor(Color.RED);
    g.fillArc(220,350,160,120, 180, 180);
    
    g.setColor(Color.BLUE);
    g.setFont(new Font("Monospaced", Font.PLAIN, 40));
    g.drawString("Great Job Math Genius!!", 30,100);
    
  }
  public static int checkUserInput()
  {
    int answer = 0;
    while ( true )
    {
      // Checks to see if the user input is an integer.
      boolean isInteger = CONSOLE.hasNextInt();
      
      while(!isInteger)
      {
        CONSOLE.next();
        System.out.println("The input was not an integer. Please try again");
        isInteger = CONSOLE.hasNextInt(); 
      }
      
      answer = CONSOLE.nextInt();
      
    
      return answer;
    }
    
  }
}
  
