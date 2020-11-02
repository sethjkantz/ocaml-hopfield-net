README.txt
Seth Kantz
skantz
C20741305
SDE1

Pledge:
On my honor I have neither given nor received aid on this exam.
   - Seth Kantz

Description:

FILE: load_both_given_and_new.caml
      - Loads sde1_sp2020.caml and sde1_sp2020_given_functions.caml for use with testing

FILE: sde1_sp2020.caml
      - Written by Seth Kantz
      - Creates the following functions to be called in testing
      	   - nextState
			      - returns and computes next state vector
	     		      - INPUT:  list float   	    - currentState
			      	        list list float     - weightMatrix
			      - OUTPUT: list float 
	   - updateN
			      - returns network state after n time steps
	     		      - INPUT:  list float    	    - currentState
			      		list list float     - weightMatrix
					int  	  	    - n
			      - OUTPUT: list float
	   - findsEquilibrium
			      - true if equilibrium occurs in the range
	     		      - INPUT:  list float  	    - initialState
			      		list list float     - weightMatrix
					int  	  	    - range
			      - OUTPUT: boolean
	   - energy
			      - returns the overall energy in the system
	     		      - INPUT:  list float	    - state
			      		list list float     - weight matrix
			      - OUTPUT: float
	   - hopTrainAstate
			      - returns weight matrix for single stored list
	     		      - INPUT:  list float	    - state
			      - OUTPUT: list list float
	   - hopTrain
			      - returns weight matrix of a list of stored states
	     		      - INPUT:  list list float	    - allStates
			      - OUTPUT:	list list
      - Creates the following helper functions that aid the above tasks
           - sizeDif
			      - helps energy
			      - returns the size difference of two lists
			      - INPUT:  list *	 	    - bigMat	- the bigger matrix
			      		list *		    - smallMat 	- the smaller matrix
			      - OUTPUT: int		    - difference btw the two  
           - genRow
			      - helps hopTrainAstate
			      - returns a row of weights for genTrain to use
			      - INPUT:  list float	    - stateRow
			      		float	    	    - iVal - float at location i
					int		    - i
					int		    - j 		
			      - OUTPUT: list float	    - single row of weights
           - genTrain
			      - helps hopTrainAstate
			      - returns a weight matrix by making a list of weight rows
			      - INPUT:  list float	    - state
			      		list float	    - curState
					int  		    - i 
			      - OUTPUT: list list float	    - weight matrix		      

           - addList
			      - helps hopTrain
			      - returns the matrix after performing matrix addition on two lists
			      - INPUT:  list float	    - list1
			      		list float	    - list2
			      - OUTPUT: list float 	    - matrix summed lists
           - addDL
			      - helps hopTrain
			      - returns summed double matrix
			      - calls itself and addList in order to add double lists
			      - INPUT:  list list float	    - list1
			      		list list float	    - list2
			      - OUTPUT: list list float	    - matrix summed lists
           - addMultDL
			      - helps hopTrain
			      - returns triple list float that contains the list list weight matrix
			      - adds its first double matrix + second + third .. + nth
			      - INPUT:  list list list float - tripList - list of double list weights
			      		list list list float - tripTail - tail of above list
			      - OUTPUT: list list list float - triple list float with one double list weight values inside 			      
           - hopCombine
			      - helps hopTrain
			      - returns a triple list of weight matrices
			      - converts a list of single states into a list of double list weight matrices
			      - INPUT:  list list	     - list of n states
			      - OUTPUT: list list list	     - list of weight matrices      


FILE: sde1_sp2020_given_functions.caml
      - Written by Dr. Schalkoff
      - Provides the following functions:
      	   - netUnit 	     - returns scalar net activation
	   - netAll  	     - returns net Activation for network
	   - hop11Activation - returns single squashed unit output
	   - hop11ActAll     - returns vector list of squashed unit outputs

FILE: sde1.log
      - Ocaml output
      - shows the output from the functions with various input provided



