# Titanic-Voyage-Rescue-Mission
A java program showing some variables and calculations
/**
 * 
 */

/**
 	File Name: LifeBoats.java
	   Author: Tinubu Damilola
		 	 Date: 14 Jun 2025 07:15:08
Description: Titanic Voyage Rescue Mission
 */
import java. util.Scanner; 

public class LifeBoats
{


	public static void main(String[] args)
	{
		/*
		 Psuedocode
		 1. Title the program
		 2. Instantiate or create a scanner object
		 3. Prompt user input
		 4. calculations
		 5. Results output
		 
		 Life Boat Capacity Analysis
		 1. Titanic embarked on Voyage on April 10, 1912 with maximum capacity of 2227 people on board
		 2. Life boats present on ship is about 20 with average capacity of 59 (20 * 59 = 1,180)
		 
		 INPUTS FROM USER
		 1. The name of the ship (possibly including spaces like HMS Endurance) 
		 2. The number of people on board the ship
		 3. The maximum number of people that can be carried by one lifeboat  
		 		assuming all the lifeboats on the ship are the same size
		 4. The actual number of lifeboats that are available on the ship
		 
		 OUTPUTS EXPECTED
		 1. The minimum number of lifeboats required to carry all the people
		 2. aThe number of people that would be rescued if the available lifeboats were filled 
		 		(but not beyond the number of people on board the ship) as well as the percentage that 
		 		this represents of all the people on board
		 3. The number of people that would drown as well as the percentage that this represents
		  	of all the people on board 
		 4. If nobody drowns, then also display the number of additional people that could be carried 
		 		by the lifeboats if they were all filled to capacity regardless of whether this number is 
		 		greater than the number of people on board. 
		 */
			// FROM PSEUDOCODE
		//1. Title Program
			System.out.println("\nLifeboat Capacity Analysis");
			System.out.println("**************************\n");
			
		//Create Scanner object for input
			Scanner scanner = new Scanner(System.in);
			
		//2. INPUTS FROM THE USER FOR SHIP DETAILS
			
			//a. The name of the ship
			 System.out.print("Name of the ship: ");
			 String shipnmame = scanner.nextLine();

			//b. The number of people on the ship
			System.out.print("Number of people on board the ship: ");
			 int totalnumberofpeople = scanner.nextInt();
			
			
			//c. The maximum number of people that can be carried by one lifeboat  
		  //assuming all the lifeboats on the ship are the same size
			 System.out.print("Maximum number of people that can be carried by one lifeboat: ");
			 int maximumnumberofpeople = scanner.nextInt();
			 
			 //d. The actual number of lifeboats that are available on board the ship
			 System.out.print("Actual number of lifeboats that are available on board the ship:");
			 int actualnumberoflifeboats = scanner.nextInt();
		
			
			 System.out.println(); // Blank line
			 
			 System.out.println("Here are the results; ");
			
			 
			 System.out.println(); // Blank line
			 
			 
			     
			 // 3. Life Boat Calculations

       // a. Minimum number of lifeboats required
			 //There are exactly enough lifeboats to rescue everyone without any additional capacity
			 int peopleOnBoard = 2227;
			 int lifeBoatCapacity = 59;
			 int lifeBoatsAvailable = 20;
			 
       int minLifeboatsNeeded = (int) Math.ceil((double) peopleOnBoard / lifeBoatCapacity);
       System.out.println("Minimum number of lifeboats required: " + minLifeboatsNeeded);
       
       // b. Calculate number of rescued people
       
       int rescuedPeople = Math.min(lifeBoatsAvailable * lifeBoatCapacity, peopleOnBoard);
       System.out.println("Number of Rescued People: " + rescuedPeople);
       double rescuePercent = 100.0 * rescuedPeople / peopleOnBoard;
       System.out.println("Percentage of people rescued: " + rescuedPeople + " (" + String.format("%.2f", rescuePercent) + "%)");
       
       // c. Calculate number of drowned people
       //There aren’t enough lifeboats to rescue everyone on board
       
       int drownedPeople = peopleOnBoard - rescuedPeople;
       double drownedPercent = 100.0 * drownedPeople / peopleOnBoard;
       System.out.printf("Number of Drowned People: %d\n", drownedPeople);
       System.out.printf("Percentage of people drowned: %d (%.2f%%)\n", drownedPeople, drownedPercent);
       
       // d. Calculate additional capacity if nobody drowns
       //There is more than enough capacity on the lifeboats to rescue everyone
       int extraCapacity = (lifeBoatsAvailable * lifeBoatCapacity) - peopleOnBoard;
       System.out.println("Additional capacity if nobody drowns: " + drownedPeople);
       
       if (drownedPeople == 0) {
         
      	 System.out.println("Additional capacity available: " + extraCapacity);

       // Display Output
      	 String result = "";

      	 result += "Minimum number of lifeboats required: " + minLifeboatsNeeded + "\n";
      	 result += "Number of Rescued People: " + rescuedPeople + "\n";
      	 result += "Percentage of people rescued: " + rescuedPeople + " (" + String.format("%.2f", rescuePercent) + "%)\n";
      	 result += "Number of Drowned People: " + drownedPeople + "\n";
      	 result += String.format("Percentage of people drowned: %d (%.2f%%)\n", drownedPeople, drownedPercent);

      	 if (drownedPeople == 0) {
      	     result += "Additional capacity available: " + extraCapacity + "\n";
      	 }

      	 // Print all at once
      	 System.out.println(result);

    
	}

	}
	}
