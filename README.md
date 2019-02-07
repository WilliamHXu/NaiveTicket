# NaiveTicket

The second Objects lab, from the BlueJ book's second chapter.

Look for the [Chapter 2 file](./doc/BlueJ-objects-first-ch2.pdf) you need in the [doc](./doc) folder.
There is 35 pages of reading and exercises in the chapter.

Work through all these exercises. You edit this file with your answers for these exercises.

### Exercise 2.1
* Create a TicketMachine object on the object bench.
* Upon viewing its methods, `getBalance`, `getPrice`, `insertMoney`, `printTicket`.
* Use `getPrice` method to view the value of the price of the tickets that was set when this object was created.
* Use `insertMoney` method to simulate inserting an amount of money into the machine.
* Use `getBalance` to check that the machine has a record of the amount inserted.
	* You can insert several separate amounts of money into the machine, just like you might insert multiple coins or notes into a real machine. Try inserting the exact amount required for a ticket. As this is a simple machine, a ticket will not be issued automatically, so once you have inserted enough money, call the `printTicket` method. A facsimile ticket should be printed in the BlueJ terminal window.
	
Completed

### Exercise 2.2
* What value is returned if you check the machine’s balance after it has printed a ticket?

0

### Exercise 2.3
* Experiment with inserting different amounts of money before printing tickets.
	* Do you notice anything strange about the machine’s behavior?
	* What happens if you insert too much money into the machine – do you receive any refund?
	* What happens if you do not insert enough and then try to print a ticket?
	
The machine will reset balance to 0 and print a ticket regardless of whatever money has been inserted. No refunds or asking for more money from the machine either way.

### Exercise 2.4
* Try to obtain a good understanding of a ticket machine’s behavior by interacting with it on the object bench before we start looking at how the `TicketMachine` class is implemented in the next section.

Good deal.

### Exercise 2.5
* Create another ticket machine for tickets of a different price.
	* Buy a ticket from that machine.
	* Does the printed ticket look different?

The printed ticket has a different price listed on the ticket

### Exercise 2.6
* Write out what you think the outer wrappers of the `Student` and `LabClass` classes might look like – do not worry about the inner part.

class Student
{ //body
}

class LabClass
{ //body
}

### Exercise 2.7
Does it matter whether we write<br>
`public class TicketMachine`<br>
or<br>
`class public TicketMachine`<br>
in the outer wrapper of a class?

* Edit the source of the `TicketMachine` class to make the change and then close the editor window.
	* Do you notice a change in the class diagram?
	* What error message do you get when you now press the compile button?
	* Do you think this message clearly explains what is wrong?

class public TicketMachine creates a <identifier> expected error at compile. The message isn't super clear to me however my guess is that the class is being evaluated with public and that TicketMachine is being evaluated as a body.

### Exercise 2.8
* Check whether or not it is possible to leave out the word `public` from the outer wrapper of the `TicketMachine` class.

Yes it is!

### Exercise 2.9
* From your earlier experimentation with the ticket machine objects within BlueJ you can probably remember the names of some of the methods – `printTicket`, for instance.
	* Look at the class definition in Code 2.1 and use this knowledge, along with the additional information about ordering we have given you, to try to make a list of the names of the fields, constructors, and methods in the `TicketMachine` class.
	* Hint: There is only one constructor in the class.

Fields: price, balance, total
Constructor: TicketMachine
Methods: getPrice, getBalance, insertMoney, printTicket

### Exercise 2.10
* Do you notice any features of the constructor that make it significantly different from the other methods of the class?

It lacks a data type in its initialization.

### Exercise 2.11
* What do you think is the type of each of the following fields?

```java
private int count;
private Student representative;
private Server host;
```

int, Student, Server

### Exercise 2.12
* What are the names of the following fields?

```java
private boolean alive;
private Person tutor;
private Game game;
```

boolean, Person, Game

### Exercise 2.13

In the following field declaration from the TicketMachine class<br>

```java
private int price;
```
does it matter which order the three words appear in?
* Edit the `TicketMachine` class to try different orderings. After each change, close the editor.
	* Does the appearance of the class diagram after each change give you a clue as to whether or not other orderings are
possible?
	* Check by pressing the compile button to see if there is an error message.
	* Make sure that you reinstantiate the original version after your experiments!

We cannot order int in front of private as doing so will result in an error and a double lattice in the BlueJ visual file.

### Exercise 2.14
* Is it always necessary to have a semicolon at the end of a field declaration?
* Once again, experiment via the editor.
* The rule you will learn here is an important one, so be sure to remember it.

Yes, otherwise the is a ";" expected error.

### Exercise 2.15
* Write in full the declaration for a field of type `int` whose name is `status`.

private int status;

### Exercise 2.16
* To what class does the following constructor belong?
```
public Student(String name)
```

Student

### Exercise 2.17
* How many parameters does the following constructor have and what are their types?
```
public Book(String title, double price)
```

2, String and double

### Exercise 2.18
* Can you guess what types some of the `Book` class’s fields might be?
* Can you assume anything about the names of its fields?

Fields might include author or pages. Those might be defined as:

private String author;
private int pages;

Work all Exercises from 2.19 to 2.58 that are **NOT** marked *Challenge exercise*.
READ upto and INCLUDING section 2.15 of this chapter.

Exercise 2.19 Suppose that the class Pet has a field called name that is of type
String. Write an assignment statement in the body of the following constructor so
that the name field will be initialized with the value of the constructor’s parameter.
public Pet(String petsName)
{
private String name = petsName;
}

Exercise 2.21 Compare the getBalance method with the getPrice method.
What are the differences between them?

the method alias as well as getPrice returns the field price while getBalance returns the field balance

Exercise 2.22 If a call to getPrice can be characterized as ‘What do tickets
cost?’, how would you characterize a call to getBalance?

How much money has been inserted?

Exercise 2.23 If the name of getBalance is changed to getAmount, does the
return statement in the body of the method need to be changed, too? Try it out within
BlueJ.

No

Exercise 2.24 Define an accessor method, getTotal, that returns the value of
the total field.

    public int getTotal()
    {
        return total;
    }

Exercise 2.25 Try removing the return statement from the body of getPrice.
What error message do you see now when you try compiling the class?

missing return statement

Exercise 2.26 Compare the method signatures of getPrice and printTicket
in Code 2.1. Apart from their names, what is the main difference between them?

the type of printTicket is void as it does not need to return a value

Exercise 2.27 Do the insertMoney and printTicket methods have return
statements? Why do you think this might be? Do you notice anything about their
headers that might suggest why they do not require return statements?

No, as there was no return promised by the void type

Exercise 2.28 Create a ticket machine with a ticket price of your choosing. Before
doing anything else, call the getBalance method on it. Now call the insertMoney
method (Code 2.6) and give a non-zero positive amount of money as the actual
parameter. Now call getBalance again. The two calls to getBalance should show
different output because the call to insertMoney had the effect of changing the
machine’s state via its balance field.

Completed

Exercise 2.29 How can we tell from just its header that setPrice is a method
and not a constructor?
public void setPrice(int ticketCost)

void specifics a method

Exercise 2.30 Complete the body of the setPrice method so that it assigns the
value of its parameter to the price field.

public void setPrice(int amount)
    {
        price = amount;
    }

Exercise 2.31 Complete the body of the following method, whose purpose is to
add the value of its parameter to a field named score.
/**
* Increase score by the given number of points.
*/
public void increase(int points)
{
	score += points;
}

Exercise 2.32 Can you complete the following method, whose purpose is to subtract the value of its parameter from a field named price?
/**
* Reduce price by the given amount.
*/
public void discount(int amount)
{
	price -=amount;
}

Exercise 2.33 Add a method called prompt to the TicketMachine class. This
should have a void return type and take no parameters. The body of the method
should print something like:
Please insert the correct amount of money.

public void prompt()
    {
        System.out.println("Please insert the correct amount of money.");
    }

Exercise 2.34 Add a showPrice method to the TicketMachine class. This
should have a void return type and take no parameters. The body of the method
should print something like:
The price of a ticket is xyz cents.
where xyz should be replaced by the value held in the price field when the method
is called.

public void showPrice()
        {
            System.out.println("The price of a ticket is " + price + " cents.");
        }

Exercise 2.35 Create two ticket machines with differently priced tickets. Do calls
to their showPrice methods show the same output, or different? How do you explain
this effect?

Yes, they are calling a different price because they are separate instanced objects

Exercise 2.36 What do you think would be printed if you altered the fourth statement of printTicket so that price also has quotes around it, as follows?
System.out.println("# " + "price" + " cents.");

The system would print "# price cents." as it would treat "price" as a String, concat the Strings, and print that value

Exercise 2.37 What about the following version?
System.out.println("# price cents.");

# and cents. are undefined to java and so it will error

Exercise 2.38 Could either of the previous two versions be used to show the
price of tickets in different ticket machines? Explain your answer.

No, the first would not display an assigned price field and the second will error.

Exercise 2.39 Modify the constructor of TicketMachine so that it no longer has
a parameter. Instead, the price of tickets should be fixed at 1000 cents. What effect
does this have when you construct ticket machine objects within BlueJ?

Our ticket machine no longer asks for a price at initialization but rather the price is 
automatically 1000.

Exercise 2.40 Implement a method, empty, that simulates the effect of removing
all money from the machine. This method should have a void return type, and its
body should simply set the total field to zero. Does this method need to take any
parameters? Test your method by creating a machine, inserting some money, printing
some tickets, checking the total, and then emptying the machine. Is this method a
mutator or an accessor?

This is a mutator with no parameters

public void empty()
        {
            total = 0;
        }

Exercise 2.41 Implement a method, setPrice, that is able to set the price of
tickets to a new value. The new price is passed in as a parameter value to the
method. Test your method by creating a machine, showing the price of tickets,
changing the price, and then showing the new price. Is this method a mutator?

public void setPrice(int amount)
        {
            price = amount;
        }

Exercise 2.42 Give the class two constructors. One should take a single parameter that specifies the price, and the other should take no parameter and set the price
to be a default value of your choosing. Test your implementation by creating machines
via the two different constructors.

        public TicketMachine(int amount)
        {
            price = amount;
            balance = 0;
            total = 0;
        }
        
        public TicketMachine()
        {
            this(1000);
        }

Exercise 2.43 Check that the behavior we have discussed here is accurate by
creating a TicketMachine instance and calling insertMoney with various actual
parameter values. Check the balance both before and after calling insertMoney.
Does the balance ever change in the cases when an error message is printed? Try to
predict what will happen if you enter the value zero as the parameter, and then see if
you are right.

It will tell you to provide a positive amount and not change the balance.

Exercise 2.44 Predict what you think will happen if you change the test in
insertMoney to use the greater-than or equal-to operator:
if(amount >= 0)
Check your predictions by running some tests. What difference does it make to the
behavior of the method?

You will be allowed to have 0 as an amount entered but the balance will not change.

Exercise 2.45 In the shapes project we looked at in Chapter 1 we used a
boolean field to control a feature of the circle objects. What was that feature? Was it
well suited to being controlled by a type with only two different values?

Whether or not the circle as visible, and in this case it is appropriate to use a boolean to express this binary field

Exercise 2.46 In this version of printTicket we also do something slightly
different with the total and balance fields. Compare the implementation of the
method in Code 2.1 with that in Code 2.8 to see whether you can tell what those
differences are. Then check your understanding by experimenting within BlueJ.

Print ticket will only take away the amount paid for the ticket from the balance and add that to the total.

Exercise 2.47 After a ticket has been printed, could the value in the balance
field ever be set to a negative value by subtracting price from it? Justify your answer.

No, balance will be at least equal if not greater than price from the if statement from
which the subtraction from the balance takes place. Thus, it will not go into the negative with the subtraction

Exercise 2.48 So far we have introduced you to two arithmetic operators, + and –,
that can be used in arithmetic expressions in Java. Take a look at Appendix D to find
out what other operators are available.

Done

Exercise 2.49 Write an assignment statement that will store the result of multiplying two variables, price and discount, into a third variable, saving.

int saving = (int) (price * discount);

Exercise 2.50 Write an assignment statement that will divide the value in total
by the value in count and store the result in mean.

double mean = total/count;

Exercise 2.51 Write an if statement that will compare the value in price against
the value in budget. If price is greater than budget then print the message ‘Too
expensive’, otherwise print the message ‘Just right’.

if (price > budget) {System.out.println("Too expensive")}
else {System.out.println("Just right")}

Exercise 2.52 Modify your answer to the previous exercise so that the message if
the price is too high includes the value of your budget.

if (price > budget) {System.out.println("Too expensive. You only have " + budget + " cents to spend.")}
else {System.out.println("Just right")}

Exercise 2.53 Why does the following version of refundBalance not give the
same results as the original?
public int refundBalance()
{
balance = 0;
return balance;
}
What tests can you run to demonstrate that it does not?

This will always return 0 as it sets balance to 0 before that. We can run this version and compare it to a test where the balance > 0.

Exercise 2.54 What happens if you try to compile the TicketMachine class with
the following version of refundBalance?
public int refundBalance()
{
return balance;
balance = 0;
}
What do you know about return statements that helps to explain why this version
does not compile?

return statements end the method and so the last two lines are unreadable statements

Exercise 2.55 Add a new method, emptyMachine, that is designed to simulate
emptying the machine of money. It should both return the value in total and reset
total to be zero.

public int emptyMachine(){
    int totalCollected = total;
    total = 0;
    return totalCollected;
}

Exercise 2.56 Is emptyMachine an accessor, a mutator, or both?

both

Exercise 2.57 Rewrite the printTicket method so that it declares a local
variable, amountLeftToPay. This should then be initialized to contain the difference
between price and balance. Rewrite the test in the conditional statement to check
the value of amountLeftToPay. If its value is less than or equal to zero, a ticket
should be printed, otherwise an error message should be printed stating the amount
still required. Test your version to ensure that it behaves in exactly the same way as
the original version.

public void printTicket()
{
    int amountLeftToPay = price - balance;
    if(amountLeftToPay <= 0) {
        // Simulate the printing of a ticket.
        System.out.println("##################");
        System.out.println("# The BlueJ Line");
        System.out.println("# Ticket");
        System.out.println("# " + price + " cents.");
        System.out.println("##################");
        System.out.println();
        // Update the total collected with the price.
        total = total + price;
        // Reduce the balance by the price.
        balance = balance - price;
    }
    else {
        System.out.println("You must insert at least: " +
            (price - balance) + " cents.");
    }
}









