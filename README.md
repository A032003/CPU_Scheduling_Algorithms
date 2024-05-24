# CPU_Scheduling_Algorithms
# First Come First Serve (FCFS)
First Come First Serve (FCFS) is a straightforward scheduling algorithm where processes are executed in the order they arrive. It's simple and easy to implement but can result in poor performance when long burst time processes are present, as these will delay shorter processes. FCFS doesn't prioritize processes and is non-preemptive, meaning once a process starts, it runs to completion. This can cause inefficiencies in scenarios with varying process lengths, making it more suitable for batch systems where process order is important.

# Round Robin with Varying Time Quantum (RR)
Round Robin (RR) with variable quantum is a scheduling algorithm that allocates CPU time to processes using a time-sharing method. Unlike the standard RR with a fixed time slice, this variant adjusts the quantum based on process needs, giving shorter bursts smaller quanta and longer bursts larger ones. Processes are maintained in a queue, and each gets a quantum of time. When its quantum expires, it moves to the queue's end, and the next process gets CPU time. This method increases efficiency by reducing average waiting times and prevents starvation by ensuring all processes get CPU time eventually.

# Shortest Process Next (SPN)
Shortest Process Next (SPN) is a non-preemptive scheduling algorithm that selects processes based on their burst time, prioritizing the shortest ones first. Processes are sorted in a queue by burst time, with the shortest at the front. This approach minimizes average waiting time since shorter processes execute quicker, reducing their wait in the queue. However, it can cause longer processes to be repeatedly delayed, potentially leading to poor overall system performance.

# Shortest Remaining Time (SRT)
Shortest Remaining Time Next (SRT) is a preemptive variant of SPN. Processes are sorted by their remaining burst time, with the shortest remaining time process executed first. If a new process arrives with a shorter remaining time than the current process, it interrupts the current one. This method is advantageous for minimizing average waiting time and is adaptable to unknown burst times since it adjusts to the remaining times dynamically.

# Highest Response Ratio Next (HRRN)
Highest Response Ratio Next (HRRN) is a non-preemptive algorithm that selects processes based on their response ratio, which is calculated by dividing the waiting time by the burst time. The process with the highest ratio executes first, ensuring longer waiting processes get prioritized. This minimizes average waiting time and adapts to unknown burst times by continuously updating response ratios as processes execute.

# Feedback (FB)
The Feedback scheduling algorithm uses multiple priority queues to allocate CPU time, prioritizing higher-priority processes. New processes are placed in appropriate queues based on their priority, and completed processes move to lower priority queues. This method efficiently handles a mix of short and long processes and varying priorities by ensuring higher-priority processes are served first while eventually executing lower-priority ones.

# Feedback with Varying Time Quantum (FBV)
Similar to Feedback, Feedback with Varying Time Quantum (FBV) uses multiple priority queues but assigns different time quanta to each level. Higher-priority processes receive longer quanta, making the algorithm more efficient by focusing CPU time on more critical tasks and less on lower-priority processes.

# Aging
Xinu, an operating system developed at Purdue University, can suffer from starvation when higher-priority processes continually preclude lower-priority ones from executing. To prevent this, an aging scheduler can be used, where each rescheduling increases the priority of all ready processes by a constant amount. This ensures that lower-priority processes eventually become the highest priority and get CPU time. During scheduling, the current process’s priority resets to its initial value, while other ready processes' priorities increment, allowing the scheduler to choose the highest priority process from all eligible ones. This method requires traversing the entire ready list during each scheduler call to update priorities and select the next process.
