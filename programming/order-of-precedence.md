# Order of Precedence 
It is necessary to be careful of the meaning of such expressions as  a + b * c 

We may want the effect as either 
   (a + b) * c 
or 
   a + (b * c) 
   
All operators have a priority, and high priority operators are evaluated before lower priority ones.

Operators of the **same priority** are evaluated from **left to right**, so that a - b - c is evaluated as ( a - b ) - c as you would expect. 

From high priority to low priority the order for all C operators is: 

     ( )  [  ]  -> .
		 !   - * & sizeof cast ++ -
		       (these are right->left)
		 * / %
		 + -
		 < <= >= >
		 == !=
		 &
		 |
		 &&
		 ||
		 ?:        (right->left)
		 = += -= (right->left)
		 ,   (comma)

Thus 
   a < 10 && 2 * b < c 

is interpreted as 
   ( a < 10 ) && ( ( 2 * b ) < c ) 
and 
   a = b = spokes / spokes_per_wheel + spares;
as 
   a = ( b = ( spokes / spokes_per_wheel ) + spares);
