import java.util.Scanner;
public class BlackJack{

  public static void main(String[] args){   
    Scanner in = new Scanner(System.in);
    Scanner e = new Scanner(System.in);
    
    System.out.println("What is your name?");
    String p = in.nextLine();
    
    System.out.println(p+" has $10.");
    System.out.println("Computer has $10.");
    
    int x = 10;
    int y = 10;
      
    int i = 1;
    while(i==1 && x>=0 && y>=0){
    
      if(x<=0){
        System.out.println("Your money ran out, Computer wins!");
        break; 
      }
      if(y<=0){
        System.out.println("Computer's money ran out,"+p+" wins!");
        break;
      }  
      
      System.out.println("How much will you bet?");
      int b = e.nextInt();
      if(b>x){
        System.out.println("It's more than what you have! "+p+" loses!");
        break;
      }
      System.out.println(p+" bets $"+b+",");
      
      int c = (int)(Math.random()*y)+1;
      System.out.println("Computer bets $"+c+". Now then let's start.");
    
      int human_card1 = (int)(Math.random()*11)+1;
      int human_card2 = (int)(Math.random()*11)+1;
      int human_total = human_card1 + human_card2;
      System.out.println(p+" got");
      System.out.println(human_card1+" and "+human_card2+".");

      for (int r=1; r<4; ++r){
        System.out.println("Do you want another card? (Y/N)");
        String s = in.nextLine();
        if(s.equals("Y")){
          human_total = human_total + (int)(Math.random()*11)+1;
          System.out.println("Now, your total number is "+ human_total+".");
        }
        if(s.equals("N")){
          break;
        }
      }
      
      System.out.println("Do you want to bet more money? (Y/N)");
      String g = in.nextLine();
      
      if(g.equals("Y")){
        System.out.println("How much will you bet?");
        int m = e.nextInt();
        int f = b + m;
        if(f>x){
          System.out.println("It's more than what you have! "+p+" loses!");
          break;
        }
        System.out.println(p+" bets $"+f+".");
      }
      
      else;
        int m = 0;
        int f = b + m;
   
      int computer_card1 = (int)(Math.random()*11)+1;
      int computer_card2 = (int)(Math.random()*11)+1;
      int computer_total = computer_card1 + computer_card2;
      System.out.println("Computer got");
      System.out.println(computer_card1+" and "+computer_card2+".");
    
      if(computer_total<=11){
        computer_total = computer_total + (int)(Math.random()*11)+1;
        System.out.println("Computer got another card. Now, Computer's total number is "+computer_total+".");
      }

      if(human_total<=21 && computer_total<human_total){
        System.out.println(p+" Wins.");
        System.out.println("Computer Loses $"+c+".");
        System.out.println(p+" has $"+(x+c)+".");
        System.out.println("Computer has $"+(y-c)+".");
        x = x+c;
        y = y-c;
      }
      else{
        System.out.println("Computer Wins.");
        System.out.println(p+" Loses $"+f+".");
        System.out.println("Computer has $"+(y+f)+".");
        System.out.println(p+" has $"+(x-f)+".");
        y = y+f;
        x = x-f;
      }
    
      System.out.println("Play again? (Y/N)");
      String a = in.nextLine();
      if(a.equals("Y")){
    
      }
      else{
        i++;
        System.out.println("It was a nice game, Bye!");
      }
    }
  }
}
