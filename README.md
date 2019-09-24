# PMHRRN-cpu-scheduling-algorithm

Pre-emptive Modified Highest Response Ratio Next (PMHRRN) is a CPU scheduling algorithm
which uses hybrid priority of each process in order to schedule it. The hybrid priority is
calculated by using the concept of Response ratio and Burst time. The response ratio, R is
considered as the internal priority of a process while the length of burst time or service time of
that process is considered to be the external priority, E. The hybrid priority of each process is
obtained by giving equal weight to both its external and internal priority. The hybrid priority, HP,
of each process is computed as follows: HP = 0.5 * R + 0.5 * E. Here R is the response ratio
which is calculated as: R = (w + s)/s where “w” is the current waiting time and “s” is the burst
time. E is the external priority of the process which is predefined (taken as an input). Processes
with the highest hybrid priority, HP, will be executed next. After the execution of a burst time, a
running process may be pre-empted if there is another process with a higher hybrid priority.
Since the priority depends on the dynamic waiting time of the process hence this algorithm
prevents Process Starvation. The pseudocode for the PMHRRN algorithm is provided below.

Referrences: Harshal Bharatkumar Parekh, Sheetal Chaudhari: A New Hybrid Process Scheduling
Algorithm Preemptive Modified Highest Response Ratio Next (PMHRRN)

http://article.sapub.org/10.5923.j.computer.20150501.01.html

Psuedocode:
1) SET AWT = 0, ATAT = 0.
2) Processes arrive at the READY QUEUE (RQ) if AT of current process <= current time.
3) Processes in RQ are sorted and assigned priority
4) Hybrid priority, HP = 0.5R + 0.5E, where R = (w + s)/s and E is the external priority.
5) IF there are multiple processes with highest HP THEN
IF processes with same highest HP arrive at same time THEN
Pi = any process with highest HP
ELSE
Pi = process with earliest arrival time among the processes
6) ELSE Pi = process with highest hybrid priority, HP
7) EXECUTE Pi for 1 CYCLE_TIME
8) IF Remaining Burst Time of current process = 0 THEN
Process Pi leaves RQ
CALCULATE WT, R, and TAT for Pi and GOTO 8
1) ELSE GOTO 3
9) IF RQ = EMPTY THEN
CALCULATE AWT, ATAT of all processes and go to 9.
2) ELSE GOTO 3
