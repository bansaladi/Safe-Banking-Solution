# Safe-Banking-Solution
A client/server model to separate the presentation of data from its internal processing and storage.

#File: AccountWithConditions
#Packaged Used:
- java.util.concurrent
- java.util.concurrent.locks

#Methods Used:
- ExecutorService (allows to execute tasks on threads asynchronously)
- ReentrantLock (used to apply the lock again and again the deposit condition is true)

#How code runs:

In the beginning, firstly executor executes deposit thread and makes a random deposit in the account. It goes to sleep for 1000ms while the withdraw is made from the account and the final amount is displayed after the deposit and withdrawl. It is similar to updating a passbook from the bank. 

#Conditions Used:
- Initially, the deposit thread runs, a lock is applied so that no other thread runs parallely.
- Once it is done, lock is removed and withdraw thread runs.
- After 1000ms sleep the deposit thread runs again and make a deposit.
- Withdrawl will be performed only if there is enough balance in the account.
- When code is executed, output shows how much deposit and withdraw is made and what is the final balance.

Other two files, AccountWithSync and AccountWithoutSync shows the difference between use of locks and without its use.
