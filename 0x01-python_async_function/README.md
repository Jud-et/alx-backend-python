Python Async Project
This project focuses on asynchronous programming in Python using asyncio. It includes several tasks to demonstrate the use of coroutines, tasks, and timing in asynchronous functions.

Tasks Overview
Task 0: The Basics of Async
Objective: Write an asynchronous coroutine wait_random that waits for a random delay between 0 and max_delay seconds and returns the delay.

How We Achieved It:

Defined an asynchronous coroutine wait_random using the async and await syntax.
Used random.uniform to generate a random delay between 0 and max_delay.
The coroutine uses await asyncio.sleep to introduce the delay before returning it.
Important Points:

Understand the async and await keywords.
Use asyncio.sleep to pause execution in an asynchronous function.
Task 1: Execute Multiple Coroutines at the Same Time with async
Objective: Create an asynchronous coroutine wait_n that spawns wait_random n times with a specified max_delay and returns a list of delays in ascending order.

How We Achieved It:

Imported wait_random from 0-basic_async_syntax.py.
Defined wait_n to create a list of n coroutines.
Used await asyncio.gather(*tasks) to execute all coroutines concurrently and gather their results.
Returned the delays after sorting them.
Important Points:

Use asyncio.gather to run multiple coroutines concurrently.
Ensure the list of results is sorted, as coroutines may complete in an unpredictable order.
Task 2: Measure the Runtime
Objective: Create a function measure_time that measures the total execution time for wait_n(n, max_delay) and returns the average time per coroutine.

How We Achieved It:

Imported wait_n and time for timing measurements.
Recorded the start and end times before and after calling wait_n.
Calculated the total execution time and divided by n to get the average time per coroutine.
Important Points:

Use time.time() to measure elapsed time.
Ensure that the timing measurements include the full duration of coroutine execution.
Task 3: Tasks
Objective: Write a function task_wait_random that takes an integer max_delay and returns an asyncio.Task object.

How We Achieved It:

Imported wait_random and used asyncio.create_task to create a task from wait_random(max_delay).
Returned the created asyncio.Task.
Important Points:

Use asyncio.create_task to create tasks from coroutines.
Understand the difference between coroutines and tasks in asyncio.
Task 4: Tasks with Multiple Coroutines
Objective: Alter wait_n to task_wait_n using task_wait_random to create tasks and return their delays in ascending order.

How We Achieved It:

Imported task_wait_random from 3-tasks.py.
Defined task_wait_n to create a list of tasks using task_wait_random.
Used await asyncio.gather(*tasks) to execute all tasks and gather their results.
Returned the list of delays after sorting.
Important Points:

Use tasks to manage multiple concurrent operations.
Ensure the results are collected and sorted properly.
Usage
To run the tasks and test the implementations, use the provided main files:

0-main.py: Tests wait_random.
1-main.py: Tests wait_n.
2-main.py: Tests measure_time.
3-main.py: Tests task_wait_random.
4-main.py: Tests task_wait_n.
Make sure to have Python 3.7+ installed and execute the main files to see the results.

Contributing
Feel free to contribute by submitting issues or pull requests.
