# StoneMasonKarel
Stanford CS106A: The goal of this algorithm is to have "Karel the Robot" fix all the columns that have been knocked down in a way that can be used on other programs. Created by BRYAN PACHECO
* File: StoneMasonKarel.java
 * --------------------------
 * The StoneMasonKarel subclass as it appears here does nothing.
 * When you finish writing it, it should solve the "repair the quad"
 * problem from Assignment 1.  In addition to editing the program,
 * you should be sure to edit this comment so that it no longer
 * indicates that the program does nothing.
 */

import stanford.karel.*;

public class StoneMasonKarel extends SuperKarel {

	// You fill in this part

	public void run() {
		if (frontIsClear()){
			repairColumns();
			moveToNextColumn();
			searchForColumns();
			lookForLastColumn();
			
		}
	}
	
	/* Karel will be looking for the sign of a beeper, once it idetifies a beepers he will
	 * know to turnLeft and face north, he will them search if the column needs repair or not*/
	
	private void repairColumns(){
		while (frontIsClear()){
			move();
			if (beepersPresent()){
				turnLeft();
				while (frontIsClear()){
					move();
					if (noBeepersPresent()){
						putBeeper();
					}
				}
			}
		}
	}
	
	/*Once he fixes the column Karel will begin the search for the next column by 
	 *looking for a beeper*/
	
	private void moveToNextColumn(){
		     turnLeft();
		while (frontIsClear()){
				move();		
				if (beepersPresent()){
					turnLeft();
				}
		
	if (beepersPresent()){
		move();
		while (frontIsClear()){
			move();
			if (noBeepersPresent()){
				putBeeper();
						}
					}	
				}
			}
	}
	/*Here Karel knows he fixed two columns so he will skip the once he fixed in search for an unfinished one*/
	private void searchForColumns(){
		turnLeft();
		move();
		while (frontIsClear()){
			move();
			if (beepersPresent()){
				move();
				while (frontIsClear()){
					move();
					if (beepersPresent()){
						turnLeft();
						while (frontIsClear()){
							move();
							if (noBeepersPresent()){
								putBeeper();
							}
						}
					}
				}
			}
		}
	}
	private void lookForLastColumn(){
		turnLeft();
		move();
		while (frontIsClear()){
			move();
			if (beepersPresent()){
				turnLeft();
				while (frontIsClear()){
					move();
							if (noBeepersPresent()){
								putBeeper();
							}
						}
					}
				}
			}
		}
