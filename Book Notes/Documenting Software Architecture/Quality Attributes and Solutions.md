 

- If you require high performance, you need to
	- Exploit potential parallelism by decomposing the work into cooperating or synchronizing processes.
	- Manage the interprocess and network communication volume and data access frequencies.
	- Be able to estimate expected latencies and throughputs.
	- Identify potential performance bottlenecks.
-   If your system needs high accuracy, you must pay attention to how the data elements are defined and used and how their values flow throughout the system.
-   If security is important, you need to
	-	Legislate usage relationships and communication restric- tions among the parts.
	-  Identify parts of the system where an unauthorized intru- sion will do the most damage.
	- Possibly introduce special elements that have earned a high degree of trust.
-   If you need to support modifiability and portability, you must carefully separate concerns among the parts of the sys- tem, so that when a change affects one element, that change does not ripple across the system.
-   If you want to deploy the system incrementally, by releasing successively larger subsets, you have to keep the dependency relationships among the pieces untangled, to avoid the “nothing works until everything works” syndrome.