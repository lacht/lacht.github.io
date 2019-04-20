#Welcome to Lacht's homepage!



## Code Review 

[Code Review video](https://youtu.be/CKUP-A3HhMI)

## Example of Software Design and Engineering
### *Narrative*

Here is the original weights program display in the Java language:
```java
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
         System.out.printf("Average weight: %.2f\n",sumOfWeight);                     
         //output the max 
         System.out.printf("Max weight: %.1f\n",max);
      return;}}
```

Here is the same weights program which has been converted into the Python language:
```python
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

```

## Example of Algorithms and Data structures
### *Narrative*

Here is an application created to calculate BMI results using python's Tkinter:
```python
from Tkinter import *
import tkMessageBox

# Setup of GUI
win = Tk()
win.title("BMI Calculator")
win.geometry("400x300")
win.resizable(FALSE, FALSE)


def validate_numeric(input):
    # Validating entries are in numeric format
    if input.isdigit():
        if input is "0":
            tkMessageBox.showerror("Error", "Value must be greater than zero.")
            return False
        else:
            return True
    elif input is "":
        return True
    else:
        tkMessageBox.showerror("Error", "Value must be in numeric format.")
        return False


def clear_text():
    # Clear text after selecting clear button
    heightFeet.delete(0, 'end')
    heightInches.delete(0, 'end')
    weightResponse.delete(0, 'end')
    heightFeet.focus()
    display_results.delete(1.0, 'end')


def calculator():
    # Perform BMI calculation
    userHeightFeet = int(heightFeet.get())
    userHeightInches = int(heightInches.get())
    userWeight = int(weightResponse.get())
    userHeight = (userHeightFeet * 12) + userHeightInches
    metricHeight = (userHeight * 0.0254)
    squareHeight = metricHeight * metricHeight
    metricWeight = userWeight*0.45359237
    results = metricWeight / squareHeight
    roundResults = str(round(results, 1))

    # Assess the BMI reading and report the results to user
    if results < 24:
        bodyMass = "Normal"
    elif results < 29:
        bodyMass = "Overweight"
    elif results < 39:
        bodyMass = "Obese"
    else:
        bodyMass = "Extreme Obesity"

    return "The BMI equals " + roundResults + "\nwhich is considered\n" + bodyMass + "."


def results_window():
    # Text window to display calculation
    display = calculator()
    display_results.delete(1.0, 'end')
    display_results.insert(END, display)
    return True


# -----Labels-----
height = Label(win, text="Enter Height: ")
height.grid(column=0, row=1)

weight = Label(win, text="Enter Weight: ")
weight.grid(column=0, row=3)

heightFeetLabel = Label(win, text="ft.")
heightFeetLabel.grid(column=2, row=1)

heightInchesLabel = Label(win, text="in.")
heightInchesLabel.grid(column=4, row=1)

weightLabel = Label(win, text="lbs.")
weightLabel.grid(column=2, row=3)

# -----Entries------
heightFeet = Entry(win, width=8)
heightFeet.grid(column=1, row=1)
reg = win.register(validate_numeric)
heightFeet.config(validate="key", validatecommand=(reg, '%P'))

heightInches = Entry(win, width=8)
heightInches.grid(column=3, row=1)
reg = win.register(validate_numeric)
heightInches.config(validate="key", validatecommand=(reg, '%P'))


weightResponse = Entry(win, width=8)
weightResponse.grid(column=1, row=3)
reg = win.register(validate_numeric)
weightResponse.config(validate="key", validatecommand=(reg, '%P'))

# -----Buttons-----
calculate = Button(win, text="Calculate", command=results_window)
calculate.grid(column=1, row=4)

clear = Button(win, text="Clear", command=clear_text)
clear.grid(column=2, row=4)

# -----Text------
display_results = Text(master=win, height=10, width=20)
display_results.grid(column=1, row=5)


win.mainloop()
```

## Example of Databases
### *Narrative*


Feel free to bookmark this page to keep an eye out for my project updates!

website theme: jekyll-theme-leapday
