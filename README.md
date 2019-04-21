# Welcome to my homepage!

## Introduction
Throughout my course work in the Computer Science program, I have been able to scaffold my learning experience with each new class that I have taken. 

In software architecture and design, I have learned that in order to develop a piece of software all steps must be conceptualized prior to any actual coding taking place.  This high-level conceptualization identifies all use-case scenarios and then maps them out using a UML diagram to provide an understanding of how the new application will fit into the current framework.  This type of design planning requires excellent communication with the stakeholders and end-users in order to identify all of the requirements, including any possible architectural framework changes, necessary for the new application to be successfully implemented.   

Throughout all of my classes, I have experienced the importance of collaborating within a team environment to successfully complete assignments and/or projects.  All of my classmates lived in different regions of the country which made effective communication all the more important.  Being able to communicate and share with other team members not only can provide a higher quality outcome for an application, but it can also expand the knowledge base for the whole group as well.


Below you will find several artifacts that I have included with this portfolio.  They demonstrate the level of my learning progression. 

## Code Review
#### Brief Description
Code review is an audit that is performed on an application’s source code. The review can be performed manually by having someone look at each line of code to spot errors and/or using tools specifically designed to catch common coding mistakes. Following code review best practices will ensure a stable application deployment. 

Initially, any new code should be worked on as a separate branch from the main line code.  During the coding process, a programmer should create unit tests to make sure that their code is functioning as designed.  They should also perform their own manual code review.  This is to ensure that errors are caught and fixed before submitting their code for final review and integration into the main code.  

#### Reason for inclusion in portfolio
The code review process helps to show the necessity of using good standard coding practices.  It also serves the purpose of helping to improve not only the functionality and security of the code being reviewed but the developer’s programming skills as well.      

#### Reflection
Some of the code review best practices that I would advocate for are:
1.	The author of the code should perform their own code review prior to any code being submitted for formal review and integration.  
2.	The author or other reviewers must create a checklist of common errors to watch out for while analyzing the code.
3.	Unit tests should be created to test how the code performs while it is running.
4.	Last but not least, to treat the programmer with respect while reviewing their code.  If there is a coding error found, the problem is with the code and not with the programmer.  Code reviews should be a time to share knowledge and grow as a team. 


Here is a short video showing my review of a program that I want to enhance for my ePortfolio:
[Code Review video](https://youtu.be/CKUP-A3HhMI)

## People's Weights Program
#### *Example of Software Design and Engineering*
#### Brief Description
The coding artifact that I used comes from the IT145 Introduction to software development course.  This class was one of the first programming classes that I took while at SNHU and the programming application was an assignment in one of the last modules for the class.  The simple Java coded program takes a series of weights entered in by the user and stores it into an array of doubles.  The program is then designed to calculate the total weight along with the max and average values from all the weights entered.  
#### Reason for inclusion in portfolio
I wanted to ultimately develop this application further to show my progression and understanding of programming, design and storage of information. This artifact is simple in execution which gives it a greater potential for overall expansion. In this first iteration, I wanted to show my knowledge of other programming languages by converting the existing Java code into a Python format.
#### Reflection
I met the objective which was to take the original Java code and convert it into Python.  Python is an intuitive, user friendly language.  Just comparing the two languages for the same application, shows that Python requires fewer statements to execute the same program. While reviewing the original Java program, I could see why such things as coding formats, commenting and naming practices are necessary. Using proper coding techniques/practices helps to quickly understand the program.  

Here is the original program displayed in the Java language:
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

Here is the program after it has been converted into the Python language and enhanced with a sort feature:
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

## BMI Calculator Application
#### *Example of Algorithms and Data structures*

#### Brief Description
The next artifact that I created was a BMI calculator.  It takes the user’s height and weight converts it into its metric equivalents.  It then performs a calculation based on the BMI formula which is BMI = kg/m^2.  This application takes end-user input via a graphical user interface. It display's the user's calculated BMI along with a description of the range where that value falls into such as Normal weight to Extreme Obesity. 
#### Reason for inclusion in portfolio
I selected this item to expand upon from my original "weights" artifact. The specific components that showcased my abilities in software development are the way the data is structured and designed to provide error-free results.  I improved upon the python application by adding a GUI framework which would be more visually appealing and user-friendly to work with.
#### Reflection
I had met my initial goal for this application. I would like to further expand upon this application and include it into a medical database application with security features. The first thing I learned while creating this project is that Python has a GUI creation tool called Tkinter.  I had previously thought Python was used for only command line-based applications. While working on this application, I faced challenges of preventing the user from entering anything other than numeric values. I corrected most of those issues except for one.  The only problem left is with blank entries which I am still working to fix.  I have the calculations reading exactly as per the NIH guidelines and it also displays the same results as their BMI calculator.   

This application was inspired by the weight's program.  It calculates an end-user's BMI results using the height and weight values entered.  It also uses Python's Tkinter to provide a graphical user interface.

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

## Database
#### *Example of Databases*

#### Brief Description
The artifact that I created for this milestone was a BMI collection for the medical records database in MongoDB. I had worked with MongoDB in Advanced Programming Concepts.  But this specific artifact was created for this portfolio as an overall extension for the BMI application.  


#### Reason for inclusion in portfolio


#### Reflection
![ERD example](https://user-images.githubusercontent.com/28314654/56473281-d79e5400-6436-11e9-96a9-544a1073fe94.png)





Feel free to bookmark this page to keep an eye out for my project updates!

website theme: jekyll-theme-leapday
