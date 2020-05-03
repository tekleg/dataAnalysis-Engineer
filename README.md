# Java 
package com.tekle2.javacore17;
// This code is perfect 2020
//Tekle's Project One 
import java.util.*;
 public class RaffleWinners {
  
	public static void main(String[] args) {
	int largestNum=1;
	int smallestNum=1;
	String userAnswer;		
	int numberGuessed = 0;
	Random generator = new Random();
	char response = 0;
	Scanner scan = new Scanner (System.in);
	System.out.println("Welcome to the Raffle Ticket");
	 
	do{ 
		
	 
	System.out.println ("What is the smallest Raffle Ticket number?");
	 smallestNum = Integer.parseInt(scan.nextLine());
				
	if(smallestNum <= 0){
				
	System.out.println ("Raffle ticket numbers must be positive.");	
	System.out.println ("What is the smallest raffle Ticket number?");
	smallestNum = Integer.parseInt(scan.nextLine());
	}
	System.out.println ("What is the largest raffle Ticket number?");
				
	largestNum = Integer.parseInt(scan.nextLine());
				
	if(0>=largestNum ) {
					
	System.out.println ("Raffle ticket numbers must be positive.");
	System.out.println ("What is the largest raffle Ticket number?");			
	largestNum = Integer.parseInt(scan.nextLine());
	}


	while(smallestNum >largestNum) {
	System.out.println ("The maxiumum must be larger than the minimum."); 
	System.out.println ("What is the smallest raffle Ticket number?");
	smallestNum = Integer.parseInt(scan.nextLine());
	        
	System.out.println ("What is the largest raffle Ticket number?");
	largestNum = Integer.parseInt(scan.nextLine());  

	}


	while( (largestNum-smallestNum) <2 )  {	                               //  At least three tickets sold! 
	System.out.println (" There must be at least three tickets sold!");
	System.out.println (" What is the smallest Raffle Ticket number?");
	smallestNum = Integer.parseInt(scan.nextLine());
		        
	System.out.println ("What is the largest Raffle Ticket number?");
	largestNum = Integer.parseInt(scan.nextLine());                
	}

	                                                                             //To genrate the three Raffle numbers
 int ticket1 = generator.nextInt(largestNum - smallestNum + 1) + smallestNum;
	 
	int ticket2 = generator.nextInt(largestNum - smallestNum + 1) + smallestNum;
	int ticket3 = generator.nextInt(largestNum - smallestNum + 1) + smallestNum;	
	 
		
	 
		
	System.out.println("The winning Raffle numbers are:");


	if(( ticket1!=ticket2) && (ticket1!=ticket3) && (ticket2 != ticket3))  {
		
	System.out.println(" \b  ticket1:" + ticket1  +  " \n \b  ticket2:" + ticket2 +  " \n \b  ticket3:" + ticket3);
							 
	System.out.println("Want to tell me your Raffle number? Enter 'y' or 'n'");
	}
	
	else{
		while((ticket1==ticket2) || (ticket1==ticket3)) {
		 ticket1 = generator.nextInt(largestNum - smallestNum + 1) + smallestNum;	
	}
		while((ticket2==ticket1) || (ticket2 ==ticket3)) {
		 ticket2 = generator.nextInt(largestNum - smallestNum + 1) + smallestNum;	
	}
		System.out.println(" \b  ticket1:" + ticket1  +  " \n \b  ticket2:" + ticket2 +  " \n \b  ticket3:" + ticket3);
				 
		System.out.println("Want to tell me your Raffle number? Enter 'y' or 'n'");
	}
	userAnswer = scan.nextLine();
	response = userAnswer.charAt(0);
		       

	if(response == 'y' || response == 'Y') {
	System.out.println("What was your number?");
	numberGuessed = Integer.parseInt(scan.nextLine());
	if(( numberGuessed == ticket1) || (numberGuessed == ticket2) || (numberGuessed ==ticket3)){
	System.out.println("You were  a winner!");
	System.out.println("Again with a new raffle? Enter 'y' or 'n'");
	}
	 
	else{                                        
	System.out.println("You were not a winner");

	}  
	}
	System.out.println("Again with a new raffle? Enter 'y' or 'n'");	
	userAnswer = scan.nextLine();
	response = userAnswer.charAt(0);
	if(response == 'n' || response == 'N') {
	System.out.println("Good bye!");}	
	}while(response == 'y' || response == 'Y');
	}
	}

	 


