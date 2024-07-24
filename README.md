<div style="text-align: justify">

# Generator vs List Comprehension in Python Analysis
The experiment and its results can be accessed in the `Generator_python_analysis.ipynb` notebook.
## Below is an easy-to-understand explanation of the working of generators vs list comprehensions in Python.

### Generator as a Lazy and Irresponsible Worker

Imagine you have a worker named Gen. Gen is a bit lazy and irresponsible:

- **Lazy**: Gen doesn't do any work unless you specifically ask him to do it.
- **Irresponsible**: He doesn't remember what he did before, and he doesn't plan ahead for what he needs to do in the future. He only focuses on the task at hand.

### Here's how Gen operates:

1. **Starts Work Only When Asked**: When you first call Gen (using a generator function), he doesn't start working right away. He waits until you explicitly tell him to get started (using `next()` or a `for` loop).

2. **Does One Task at a Time**: When you ask Gen to work, he does one small task (reaches a `yield` statement), then stops and waits for the next instruction.

3. **Forgets the Past**: After completing a task, Gen doesn't keep a log of what he did. He just waits for the next task. When you ask him to continue, he picks up from where he left off without remembering the previous tasks.

4. **No Long-term Plans**: Gen doesn't plan for future tasks. He only focuses on the current task at hand. Once he's done, he stops and waits for the next instruction.

5. **Stops When Done**: When there are no more tasks to do (no more `yield` statements in the generator), Gen tells you he's done and stops working completely.

### Example Scenario

Imagine you're managing a list of tasks that need to be processed one by one:

#### List Comprehension Worker (Diligent Worker)
**ListWorker**: This worker sits down and completes all the tasks at once, writes down the results, and hands you the complete list. This is like a list comprehension in Python. It uses a lot of memory because it stores all the tasks' results.

#### Generator Worker (Gen, the Lazy and Irresponsible Worker)
**GenWorker**: Gen, on the other hand, does only one task at a time when you ask him to. He doesn't store the results of all the tasks. He simply does one task, gives you the result, and waits for the next task. This is like a generator in Python.

### Code Example

Here’s how it looks in Python code:

```python
def gen_worker():
    yield "Task 1 done"
    yield "Task 2 done"
    yield "Task 3 done"

# Create Gen (the generator worker)
gen = gen_worker()

# Ask Gen to do tasks one by one
for task in gen:
    print(task)

# prints yeild statements one by one without storing results in memory
```
### Summary

- Gen (the Generator): Only works when told to (lazy), doesn't remember past tasks (irresponsible), and doesn't store results.
- ListWorker: Completes all tasks at once and stores all results, which uses more memory.

In short, a generator in Python is like a lazy and irresponsible worker who does only what he’s told at the moment, forgets the past, and doesn’t plan for the future. This makes generators memory efficient for handling large amounts of data one piece at a time (useful in data streaming cases).

</div>