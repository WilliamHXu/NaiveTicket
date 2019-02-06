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






