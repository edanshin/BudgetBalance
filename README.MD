# We've made the balance history readonly for the auto marking.
BALANCE_HISTORY = [107, 201, 201, 225, 216]

def inc_or_dec(days_ago):

  # Avoid -1 because that slice will only have 1 balance!
  for day in range(-days_ago, -1):
    balance_slice = BALANCE_HISTORY[day : day + 2]
    difference = balance_slice[1] - balance_slice[0]
    if difference > 0:
      print(f'Balance from {abs(day)} days ago INCREASED!')
    elif difference < 0:
      print(f'Balance from {abs(day)} days ago DECREASED!')


d = int(input('How many days of data? '))
inc_or_dec(d)



Someone's written a program to help balance their personal budget.

The program is supposed to compare adjacent daily balances going back over a number of days, and show whether the balance increased, decreased, or stayed the same.

The program isn't working (it has a bunch of errors, in fact)!

We'd like you to:

    Explain in a comment what's wrong with the code. Is slicing the best approach?
    Fix the code so it works as intended, and
    Make it more maintainable for the next person (comments, better variable names, etc.).

Here's what should be printed when the user wants balances going back 3 days:

How many days of data? 3
Balance from 3 days ago INCREASED!
Balance from 2 days ago DECREASED!

​
And here's another example where the user wants all the data (7 days worth):

How many days of data? 7
Balance from 5 days ago INCREASED!
Balance from 4 days ago stayed THE SAME!
Balance from 3 days ago INCREASED!
Balance from 2 days ago DECREASED!
