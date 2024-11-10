# CPU Scheduling Algorithm: Priority-Based Scheduling

A Python implementation of Priority-Based CPU Scheduling with Gantt chart visualization, turnaround, and waiting time calculations.

## Features

- The program interacts with the user to input process details such as arrival time, burst time, and priority.
- Displays a table containing detailed information about each process, including arrival time, burst time, completion time, turnaround time, and waiting time.
- Displays a dynamic Gantt chart showing the execution timeline of processes.

## Explanation of the Code

1. **Process Class**

   - The `Process` class is used to represent a process in the system. Each process has the following attributes:
     - `pid`: Process ID (a unique identifier for the process).
     - `arrival_time`: The time at which the process arrives in the system.
     - `burst_time`: The time required for the process to complete its execution.
     - `priority`: The priority of the process (lower values indicate higher priority).
     - `completion_time`: The time at which the process completes its execution.
     - `turnaround_time`: The total time from the process arrival to its completion (`completion_time - arrival_time`).
     - `waiting_time`: The time the process spends waiting for CPU time (`turnaround_time - burst_time`).

2. **Priority Scheduling Algorithm**

   The `priority_scheduling` function simulates the priority-based scheduling of processes. It follows these steps:

   - Sorts processes by arrival time, then by priority.
   - Processes are selected based on their priority and executed until completion.
   - If no processes are ready to execute, the algorithm increments the time.
   - For each executed process, it calculates the completion time, turnaround time, and waiting time.

3. **Plotting Functions**

   - `plot_gantt_chart`: This function uses Plotly to create a Gantt chart to visually display the execution timeline of each process.
   - `plot_process_details`: This function generates a table of process details (e.g., arrival time, burst time, completion time) using Plotly.

4. **User Interaction**

   The function `get_user_input` prompts the user to input:

   - The number of processes.
   - For each process: arrival time, burst time, and priority.

   It collects these inputs and creates a list of `Process` objects which are then passed to the priority scheduling algorithm.

## Running the Program

1. **Dependencies**

   The project requires the following Python libraries:

   - `pandas`
   - `numpy`
   - `plotly`

   To install these dependencies, use the following command:

   ```bash
   pip install -r requirements.txt
   ```

2. **Running the Notebook**
   - Open the `main.ipynb` notebook in a Jupyter Notebook environment.
   - Run each cell sequentially to execute the program.
   - The program will prompt you to enter the number of processes and the details for each process.
   - After inputting the process details, the program will:
     1. Display the **average turnaround time** and **average waiting time**.
     2. Show a **Gantt chart** of process execution.
     3. Display a **table** with detailed process information.
