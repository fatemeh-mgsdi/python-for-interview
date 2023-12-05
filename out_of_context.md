## Multithreading vs multiprocessing
Let’s say you have to get done 2 very important tasks in one day:

1- Get a passport

2- Get a presentation done


Now, the problem is that task-1 requires you to go to an extremely bureaucratic government office that makes you wait for 4 hours in a line to get your passport. Meanwhile, task-2 is required by your office, and it is a critical task. Both must be finished on a specific day.

### Case 1: Sequential Execution
Ordinarily, you will drive to passport office for 2 hours, wait in the line for 4 hours, get the task done, drive back two hours, go home, stay awake 5 more hours and get presentation done.


### Case 2: Concurrent Execution
But you’re smart. You plan ahead. You carry a laptop with you, and while waiting in the line, you start working on your presentation. This way, once you get back at home, you just need to work 1 extra hour instead of 5.

In this case, both tasks are done by you, just in pieces. You interrupted the passport task while waiting in the line and worked on presentation. When your number was called, you interrupted presentation task and switched to passport task. The saving in time was essentially possible due to interruptability of both the tasks.

### Why the Confusion Exists?

Confusion exists because dictionary meanings of both these words are almost the same:

1- Concurrent: existing, happening, or done at the same time(dictionary.com)

2- Parallel: very similar and often happening at the same time(merriam webster).

Yet the way they are used in computer science and programming are quite different. Here is my interpretation:

Concurrency: Interruptability

Parallelism: Independentability

So what do I mean by above definitions?

I will clarify with a real world analogy. Let’s say you have to get done 2 very important tasks in one day:

1- Get a passport

2- Get a presentation done

Now, the problem is that task-1 requires you to go to an extremely bureaucratic government office that makes you wait for 4 hours in a line to get your passport. 

Meanwhile, task-2 is required by your office, and it is a critical task. Both must be finished on a specific day.

#### Case 1: Sequential Execution
Ordinarily, you will drive to passport office for 2 hours, wait in the line for 4 hours, get the task done, drive back two hours, go home, stay awake 5 more hours and get presentation done

### Case 2: Concurrent Execution
But you’re smart. You plan ahead. You carry a laptop with you, and while waiting in the line, you start working on your presentation. This way, once you get back at home, you just need to work 1 extra hour instead of 5.

In this case, both tasks are done by you, just in pieces. You interrupted the passport task while waiting in the line and worked on presentation. When your number was called, you interrupted presentation task and switched to passport task. The saving in time was essentially possible due to interruptability of both the tasks.

Concurrency, IMO, can be understood as the "isolation" property in ACID. Two database transactions are considered isolated if sub-transactions can be performed in each and any interleaved way and the final result is same as if the two tasks were done sequentially. Remember, that for both the passport and presentation tasks, _you are the sole executioner_

### Case 3: Parallel Execution
Now, since you are such a smart fella, you’re obviously a higher-up, and you have got an assistant. So, before you leave to start the passport task, you call him and tell him to prepare first draft of the presentation. You spend your entire day and finish passport task, come back and see your mails, and you find the presentation draft. He has done a pretty solid job and with some edits in 2 more hours, you finalize it.


Now since, your assistant is just as smart as you, he was able to work on it independently, without needing to constantly ask you for clarifications. Thus, due to the independentability of the tasks, they were performed at the same time by two different executioners

_Still with me? Alright..._

They solve different problems. Concurrency solves the problem of having scarce CPU resources and many tasks. So, you create threads or independent paths of execution through code in order to share time on the scarce resource. Up until recently, concurrency has dominated the discussion because of CPU availability.


Parallelism solves the problem of finding enough tasks and appropriate tasks (ones that can be split apart correctly) and distributing them over plentiful CPU resources. Parallelism has always been around of course, but it's coming to the forefront because multi-core processors are so cheap.


**Concurrency** => When multiple tasks are performed in overlapping time periods with shared resources (potentially maximizing the resources utilization).


**Parallel** => when single task is divided into multiple simple independent sub-tasks which can be performed simultaneously

![Screenshot from 2023-12-05 13-10-33](https://github.com/fatemeh-mgsdi/crypto-buyer-api/assets/33480382/1f71fef1-c486-483e-9acc-3a7e0df4c655)


To recap, concurrency can be seen as a **property** of a system or program and refers to how a single CPU (core) can make progress on multiple tasks **seemingly** at the same time (i.e. concurrently) while parallelism is the actual **run-time behaviour** of executing at least two tasks literally at the same time, in parallel. Additionally, it is important to highlight that b**oth concurrency and parallelism** could be combined during task execution. In fact, we could have all sort of combinations


