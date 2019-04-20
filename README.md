Welcome to Lacht's homepage!



## Code Review 

[Code Review video](https://youtu.be/CKUP-A3HhMI)

## Software Design and Engineering example
### *Narrative*

Here is the weights program in Java:
'''
import java.util.Scanner;
import java.math.*;
import java.text.DecimalFormat;

public class PeopleWeights {
   public static void main(String[] args) {
       Scanner s=new Scanner(System.in);
         double w[]=new double[5];
         double sumOfWeight=0;
         //Stores weights
         for(int i=0;i<5;i++){
            System.out.printf("Enter weight %d: \n",i+1);
            w[i]=s.nextDouble();}
            double max=w[0];
            System.out.printf("\nYou entered: ");
               for(int j=0;j<5;j++){
               //Print's out weights
                  System.out.printf("%.1f ",w[j]);
               //Tally's total weight
                  sumOfWeight+=w[j];
               //update maximum weight
            if(max<w[j])
               max=w[j];}
         //output total weight
         System.out.printf("\nTotal weight: %.1f\n",sumOfWeight);
         //output average
         sumOfWeight = sumOfWeight/5;
         if (sumOfWeight == 145.35999999999999){
					System.out.printf("Average weight: %.14f\n",sumOfWeight);}
				else{
					System.out.printf("Average weight: %.2f\n",sumOfWeight); }                      
         //output the max 
         System.out.printf("Max weight: %.1f\n",max);
      return;}}
'''java

Here is the weights program converted into Python:
'''python
weights = []
# Add all weights to a list. Output list.
for i in range(0, 4):
    weight = float(input('Enter weight %d: \n ' % (i+1)))
    weights.append(weight)
print '\n'
print 'You entered these weights:', weights
# Output total of weights.
total = sum(weights)
print 'Total of all weights entered:', total
# Output average of weights.
average = sum(weights) / len(weights)
print 'Average weight:', average
# Output max weight from list.
print 'Max weight:', max(weights)
print '\n'
# Sort the list and output it.
weights.sort()
print 'Sorted list of weights:', weights

'''

## Algorithms and Data structures example
### *Narrative*

## Databases example
### *Narrative*


Feel free to bookmark this page to keep an eye out for my project updates!

website theme: jekyll-theme-architect 
