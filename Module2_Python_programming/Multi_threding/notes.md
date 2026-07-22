
    ===============
    Multi Threading
    ===============

** A program is a set of instructions written to perform a particular task.

Ex:

        -- calculator program
        -- bank-application program
        -- youtube application
        -- Chat application

** When we execute a any program, the operating system creates a process.

============================
What is a Process?
============================

** A process is a program that is currently running in our machine.

** for example, when you open 

		-- Google Chrome
		-- PyCharm IDE
		-- Zoom software
		-- Notepad

** Each application runs as a separate process.

** Every process has its own 

		-- Memory
		-- Variables
		-- Resources
		-- Execution Environment


======================
## What is a Thread?
======================

** A thread is a small unit of execution inside a program/process.

** A single thread can contain one more more threads.

** For example, consider any web application

	- first user trying to login
	- second user watching products
	- third user doing payment
	- foruth user cancelling order

Note: Multiple users are using same application at a time (in the background multiple threads are running).	


===================
Process vs Thread
===================

** Process

		-- Process means a running application
		-- Every process will have seperate memory
		-- Creating a process is expensive interms of memory
		-- Process to process communication slow
		-- Once process can have multiple threads

** Thread 

		-- Unit of execution inside the process
		-- Multiple threads will share the memory
		-- Threads are light weight
		-- Threads communication is faster
		-- A thread always belongs to a process.


=======================
What is Multitasking?
=======================		

** ** Multitasking means performing multiple tasks during the same period.


** There are two major types of multitasking:

########### 1: Process based multi tasking

** Multiple programs run at the same time

		-- Play music
		-- write code in pycharm
		-- download file
		-- upload file

** Each application usaly runs as seperate process.		


########### 2: Thread based multi tasking

** Multiple tasks run inside the same program.

		--- download a file
		--- show download progress
		--- Take user request
		--- save user data to database

** These tasks can be handled using different threads.

** To implement Thread based multi-tasking we should know about Multi-Threading.


========================
What is Multithreading
========================

** Multi-threading means executing multiple threads within the same process.

** when we have multiple independent tasks, we can use multi-threading to execute them parallelly.


==================
Real-Life Example
===================

** Imagine a restaurant with only one employee.

        -- Take the customer's order
        -- Prepare the food
        -- Serve the food
        -- Collect payment

The second customer must wait until all the work for the first customer is completed.

This is similar to single-threaded execution.

Now imagine the restaurant has multiple employees:

         -- employee-1 takes orders
         -- employee-2 prepares food
         -- employee-3 serves food
         -- employee-4 collects payments

** Multiple activities can happen at the same time. This is similar to Multi Threading.

** Each employee is represented as one Thread. 


===============
Main Thread
===============

** Every Python program starts with one default thread called the main thread.

** Python provides the "threading" module for multithreading.

--------

import threading

print("Current Thread :", threading.current_thread())
print("Thread Name:", threading.current_thread().name)
print("Active Thread Count :", threading.active_count())

----------

=============================
Creating Threads in Python
=============================

** Python provides the "threading" module for multithreading.

** We need to "import threading" module for multi threading...

** A thread can be created using the "Thread" class.


-------------

import threading
import time

def task_1():
    print("task-1 started")
    time.sleep(3)
    print("task-1 finished")

def task_2():
    print("task-2 started")
    time.sleep(2)
    print("task-2 finished")

thread1 = threading.Thread(target=task_1)
thread2 = threading.Thread(target=task_2)

thread1.start() # Wt-1
thread2.start() #Wt-2

----------------------