Lab 4
Static Methods and Conditionals
In this lab, you will continue your practice writing methods and classes by creating a class that is not a subclass (other than of Object), writing static methods, and writing conditional statements.

If you did not join the recitation, you need to complete the first 3 tasks (including task 3 with all steps).

Task 1. Assigning Lab Partners
The first thing that will occur in this lab is the assigning of lab partners. The teaching assistants in the recitation will pair you with another student.

Rules For The Lab
Your grade will be determined by how well you work as a member of a team. You will play two different roles in the lab. You will either be the driver or navigator.

driver: The person typing at the keyboard.
navigator: The person watching for mistakes, making suggestions, and thinking ahead.
Important: The driver is the only one who may do the typing. The navigator must not jump in and start editing.
Choose one of you to begin as the driver. The other will be the navigator, and the lab will tell you when to switch roles.

You do not have to complete all the tasks by the end of lab, but you do have to make a good effort.
The only ways to lose points when working as a team is 1) you do not show up on time, 2) you goof off, 3) you are the navigator and you take over editing the document from the driver, or 4) you sit quietly as the navigator and never offer suggestions.

As in last week's lab, you will write a class that you will submit at the end of lab. You do not have to complete all the tasks by the end of the lab because you are being graded on how well you work as a team. You do have to make a good effort and work for the entire 50 minute lab to get full credit.

Submitting the Lab
If you are new to programming, your goal is to make it to Step 5 of Task 3 during the lab session. If you are having trouble with Steps 1 through 4, be sure to ask the lab assistant for help so that you have enough time to work on Step 5 and hopefully get to start Task 4.
Task 2. Introductions and Starting DrJava
If you have a lab partner, tell your lab partner your name as well your favorite place where you are zooming in from.

Choose one of you to start as the driver, and launch DrJava.

Task 3. Programming Some Static Methods and Conditional Statements.
Step 1
Write a class called Lab4. Since Lab4 is not going to extend another class (other than Object), you begin the class with
public class Lab4 {

Save the class in a file called Lab4.java.
Remember to put a comment above the class declaration that includes your name and your lab partner's name.

Step 2
Write the following public static method. (Put "public" and "static" before the return type and method name.) The method should have two inputs, each of type double.

  /** Input two doubles and return the larger of the two doubles. */
  double maxDouble
Do you remember how to give inputs to a method? You will need an conditional statement in the body of the method. Try to write your method so that the body is just of the form:
if (do some test) {
  what you should do if the test passes
}
else {
  what you should do if the test fails
}
Compile it, and fix any errors.
Test Lab4.maxDouble in the Interactions pane.

Step 3
Add the following method to class Lab 4:

  /** Input three doubles and return the middle value of the three. */
  double middleValue
So, if the values entered are 1.5, 0.2, and 9.3, the middle value would be 1.5. Hint: You are going to need more than one conditional to complete this task.
Compile it and fix and errors.

Test Lab4.middleValue in the Interactions pane.

Step 4
Switch roles: the navigator should drive and the driver should navigate. You can either save your Java file (ending in a .java extension) to the Google drive and share it with your partner, or you can create a shared Google doc and copy the contents of the editor window into the document.

Add the following method to class Lab4:

  /** Input a double value and return the closest int value.  The int value should be rounded
    * so that if the fractional value is 0.5 or greater, it rounds up and if it is less than 0.5
    * it rounds down.
    */
  int roundDouble
You can write this method without using a conditional statement, and using a mathematical operation instead. See if you can find the short way to write it. If not, you may use a conditional statement.
Step 5
Here is a bigger challenge. The method roundDouble does what is called "biased rounding" because it always rounds 0.5 up. For "unbiased rounding", if the fraction part is exactly 0.5 it should only be rounded up half of the time. The accepted solution is to always round to the even integer, so 3.5 becomes 4 but 2.5 becomes 2. Create a method unbiasedRoundDouble that does unbiased rounding. Remember to include a comment above your method. This method will require an if statement.

Show your roundDouble and unbiasedRoundDouble methods to your lab assistant.

Task 4. A Complicated Conditional
Switch roles: the navigator should drive and the driver should navigate.

We will end the lab with an even larger challenge. This routine requires a fairly complicated conditional statement(s). To help you see how to reason through the logic, we will create this one in stages.

Step 1. Writing down the comment and header
Add the following method header, including the comment:

  /**
   * Return true of the given date/time is daylight savings.
   * Daylight savings time begins 2am the second Sunday of March and ends 2am the first Sunday of November.
   *
   * @param month - represents the month with 1 = January, 12 = December
   * @param date - represents the day of the month, between 1 and 31
   * @param day -  represents the day of the week with 1 = Sunday, 7 = Saturday
   * @param hour - represents the hour of the day with 0 = midnight, 12 = noon
   *
   * Precondition: the month is between 1 and 12, the date is between 1 and 31, the day is between 1 and 7
   *                and the hour is between 0 and 23.
   */
  public static boolean isDayLightSavings(int month, int date, int day, int hour) {
Step 2. Getting rid of the easy cases.
When faced with a complicated logical statement, it is often best to do things in pieces. First, write an if statement that returns false if the month is January, February, or December, and it returns true if the month is April, May, June, July, August, September, or October. You can return either true or false if the month is March or November.

Put a little thought in it because you can accomplish this with both a very long and a rather short if statement.

Important: Test your code. Call Lab4.isDayLightSavings(...) with different values for the month from 1 to 12 and make sure it returns the correct value. If it does not, fix your code. Hint: Use the up arrow on the interactions pane to avoid lots of typing.

Step 3. Handle one of the tricky cases
Switch roles: the navigator should drive and the driver should navigate.

Now add an additional part to your conditional statement to handle the month of November. (I suggest making a test to see if the month is November, and make your then-statement a compound statement to handle all the possibilities for that month.)

First, try to tell from the day and date parameters if this is the first Sunday of the month. If it is, the method should return true if the hour is less than 2 and false if the hour is 2 or greater.

Second, modify your if statement so that if the day/date combination falls before the first Sunday, your method returns true, and if it falls after the first Sunday, the method returns false. Take a little time thinking about this part. You may be able to figure out a short mathematical way to test this.

Important: Test your code. First rerun the tests you did in the previous step for the different months (except for March and November) to make sure the code still works correctly. Then, test Sunday for dates 1 through 14 and hours 1 and 2 to make sure it recognizes the first Sunday from other Sundays and that it switches answers at hour 2. Finally, test non-Sunday days and various dates to make sure it recognizes day/date combinations that fall before the first Sunday and those that do not.

When you finish, show your code to your lab instructor. Because there are lots of ways to do this, be prepared to explain why the logic you did is correct.

Step 4. Handle the other tricky case
Switch roles: the navigator should drive and the driver should navigate.

Now try adding the cases for March. The code will be very similar to the code for November, but there will need to be some adjustment because you now need to deal with the change happening on the second Sunday instead of the first. In particular, make sure your code distinguishes the second Sunday from the first and later Sundays, and it can tell if a day/date combination falls before the second Sunday.

Task 5. Finishing Up
Both you and your lab partner should submit the Lab4.java file. Please do that now.

Be certain to submit the file named Lab4.java and not the one named Lab4.java~ nor the one named Lab4.class.
