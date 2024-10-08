# Sunny User Guide
## Product Introduction
Sunny is my dog. She is kinda smart so she can help you 
keep track of your tasks, check out the instructions below
to find out more!


## Product User Interface 
![Image of the actual user interface](Ui.png)

## Getting Started
To get started with Sunny, follow these steps:

1. Ensure you have Java 17 or above installed in your Computer.
2. Under GitHub Releases, download the latest version of the jar file of the sunny chatbot (named sunny.jar).
3. From your home directory, navigate to the Downloads folder using the cd command in the terminal (e.g. cd Downloads).
4. Run the command java -jar sunny.jar. A GUI similar to the one provided above under Product User Interface should 
   appear.
5. You can now interact with Sunny! Full list of features of sunny are included below.
## Features

>Notes about command format
> 
> - Words in UPPERCASE are parameters to be supplied by the user
> - If command is entered incorrectly, 
> you will recieve a `invalid command:((`. It could be due to
>   - wrong command format
>   - wrong date format
>   - invalid date
> - If no command is entered, the system will prompt
> you with `Please specify a task`




### 1. Adding deadlines: `deadline`

Add a task with deadline.

Format: `deadline TASKDESCRIPTION /by YYYY-MM-DD`  
- TASKDESCRIPTION: name of the task
- /by YYYY-MM-DD: due date of the task

Example: `deadline buy grocery /by 2024-09-22`

Example output:
```
Got it! added the task:  
[D][] buy grocery (by: 20024-09-22)  
Now you have 2 tasks in the list
```

### 2. Adding to do tasks: `todo`

Add a task.

Format: `todo TASKDESCRIPTION`
- TASKDESCRIPTION: name of the task

Example: `todo buy grocery`

Example output:
```
Got it! added the task:  
[T][] buy grocery 
Now you have 2 tasks in the list
```

### 3. Adding events: `event`

Add a event with start and end date specified. 
Event is considered a subset of task.

Format: `event TASKDESCRIPTION /from YYYY-MM-DD /to YYYY-MM-DD`
- TASKDESCRIPTION: name of the task
- /from YYYY-MM-DD: start date of the event
- /to YYYY-MM-DD: end date of the event

Example: `event buy grocery /from 2024-09-22 /to 2024-09-23`

Example output:
```
Got it! added the task:  
[E][] buy grocery (from: 2024-09-22 to: 2024-09-23)
Now you have 2 tasks in the list
```

### 4. Listing tasks: `list`

List all tasks, both marked and unmarked

Format: `list`

Example output:
```
1. [T][] buy grocery
2. [D][] do homework (by: 2024-09-26)
3. ...
```

### 5. Finding tasks: `find`

Finding a specific task through the task description

Format: `find TASKDESCRIPTION`
- TASKDESCRIPTION: name of the task

Example: `find eat lunch`

Example output:
```
1. [T][] eat lunch with friend
3. [T][] eat lunch with sister
```


### 6. Completing a task: `mark`

Marking a task as complete in the list.

Format: `mark TASKNUMBER`
- TASKNUMER: number of the task in the list. Call `list` 
to find out task number

Original output:
```
2. [T][] eat lunch with friend
```
Example call:
`mark 2`  

Final output: 

```
Marked the task as done
[T][x] eat lunch with friend
```

### 7. Undoing a task: `unmark`

undoing a marked task in the list.

Format: `unmark TASKNUMBER`
- TASKNUMER: number of the task in the list. Call `list`
  to find out task number

Original output:
```
2. [T][x] eat lunch with friend
```
Example call:
`unmark 2`

Final output:

```
Task undone
[T][] eat lunch with friend
```

### 8. Deleting tasks: `delete`

Deleting a task from the list.

Format: `delete TASKNUMBER`
- TASKNUMER: number of the task in the list. Call `list`
  to find out task number

Original output:
```
2. [T][x] eat lunch with friend
```
Example call:
`delete 2`

Final output:

```
Got it! Removed the task:
[T][] eat lunch with friend
Now you have 2 tasks in the list
```

### 9. Snoozing tasks: `snooze`

Snooze the deadline for tasks. 
Only applicable to tasks with deadlines.

Format: `snooze TASKNUMBER /by YYYY-MM-DD`
- TASKNUMER: number of the task in the list. Call `list`
  to find out task number
- /by: new due date for the task

Original output:
```
2. [D][] buy grocery (by: 2024-09-19)
```
Example call:
`snooze /by 2024-09-20`

Final output:

```
snoozed the task
[D][] buy grocery (by: 2024-09-20)
```