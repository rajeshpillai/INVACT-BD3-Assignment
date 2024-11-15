# BD3 - Assignment

AirFlow Task Management System
Objective

Airflow is a company that is trying to create a task management system for its users. In this system, you need to add tasks, edit the priority and text of tasks, delete tasks, read the current state of tasks, sort tasks by priority, and filter tasks by priority.
Data Structure

let tasks = [
  { taskId: 1, text: 'Fix bug #101', priority: 2 },
  { taskId: 2, text: 'Implement feature #202', priority: 1 },
  { taskId: 3, text: 'Write documentation', priority: 3 }
];

Note: Don’t forget to add:

```
let cors = require('cors');

app.use(cors());
```

Endpoint 1. Add a Task to the Task List

Objective: Add a new task to the task list using the provided details.

Endpoint: /tasks/add

Query Parameters:

    taskId: The ID of the task (integer).

    text: The description of the task (string).

    priority: The priority of the task (integer).

Your Task: Create a function that will add a new task to the task list using the details provided in the query parameters.

Example Call:

<http://localhost:3000/tasks/add?taskId=4&text=Review%20code&priority=1>

Expected Output:

{
        tasks: [
          { 'taskId': 1, 'text': 'Fix bug #101', 'priority': 2 },
          { 'taskId': 2, 'text': 'Implement feature #202', 'priority': 1 },
          { 'taskId': 3, 'text': 'Write documentation', 'priority': 3 },
          { 'taskId': 4, 'text': 'Review code', 'priority': 1 }
        ]
}



Endpoint 2. Read All Tasks in the Task List

Objective: Return the current list of tasks.

Endpoint: /tasks

Your Task: Create a function that will return the current state of the task list.

Example Call:

<http://localhost:3000/tasks>

Expected Output:

{
        tasks: [
          { 'taskId': 1, 'text': 'Fix bug #101', 'priority': 2 },
          { 'taskId': 2, 'text': 'Implement feature #202', 'priority': 1 },
          { 'taskId': 3, 'text': 'Write documentation', 'priority': 3 }
        ]
}



Endpoint 3. Sort Tasks by Priority

Objective: Sort tasks by their priority in ascending order.

Endpoint: /tasks/sort-by-priority

Your Task: Create a function that will sort the tasks by their priority in ascending order.

Example Call:

<http://localhost:3000/tasks/sort-by-priority>

Expected Output:

{
        tasks: [
          { 'taskId': 2, 'text': 'Implement feature #202', 'priority': 1 },
          { 'taskId': 1, 'text': 'Fix bug #101', 'priority': 2 },
          { 'taskId': 3, 'text': 'Write documentation', 'priority': 3 }
        ]
}



Endpoint 4. Edit Task Priority

Objective: Edit the priority of an existing task based on the task ID.

Endpoint: /tasks/edit-priority

Query Parameters:

    taskId: The ID of the task (integer).

    priority: The new priority of the task (integer).

Your Task: Create a function that will update the priority of a task based on the task ID.

Example Call:

<http://localhost:3000/tasks/edit-priority?taskId=1&priority=1>

Expected Output:

{
        tasks:[
          { 'taskId': 1, 'text': 'Fix bug #101', 'priority': 1 },
          { 'taskId': 2, 'text': 'Implement feature #202', 'priority': 1 },
          { 'taskId': 3, 'text': 'Write documentation', 'priority': 3 },
        ]
}



Endpoint 5. Edit/Update Task Text

Objective: Edit the text of an existing task based on the task ID.

Endpoint: /tasks/edit-text

Query Parameters:

    taskId: The ID of the task (integer).

    text: The new text of the task (string).

Your Task: Create a function that will update the text of a task based on the task ID.

Example Call:

<http://localhost:3000/tasks/edit-text?taskId=3&text=Update%20documentation>

Expected Output:

{
        tasks: [
          { 'taskId': 1, 'text': 'Fix bug #101', 'priority': 2 },
          { 'taskId': 2, 'text': 'Implement feature #202', 'priority': 1 },
          { 'taskId': 3, 'text': 'Update documentation', 'priority': 3 }
        ]
}



Endpoint 6. Delete a Task from the Task List

Objective: Delete a task from the task list based on the task ID.

Endpoint: /tasks/delete

Query Parameters:

    taskId: The ID of the task to be deleted (integer).

    Note: You’ll have to update the original array with the results of .filter() method. For example tasks = task.filter(...)

Your Task: Create a function that will remove a task from the task list based on the task ID.

Example Call:

<http://localhost:3000/tasks/delete?taskId=2>

Expected Output:

{
        tasks: [
          { 'taskId': 1, 'text': 'Fix bug #101', 'priority': 2 },
          { 'taskId': 3, 'text': 'Write documentation', 'priority': 3 }
        ]
}



Endpoint 7. Filter Tasks by Priority

Objective: Return tasks that match a specified priority.

Endpoint: /tasks/filter-by-priority

Query Parameters:

    priority: The priority to filter tasks by (integer).

Your Task: Create a function that will return tasks that match a specified priority.

Example Call:

<http://localhost:3000/tasks/filter-by-priority?priority=1>

Expected Output:

{
        tasks: [
          { taskId: 2, text: 'Implement feature #202', priority: 1 },
        ]
}
