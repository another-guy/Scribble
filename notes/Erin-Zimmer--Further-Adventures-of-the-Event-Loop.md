# Erin Zimmer: Further Adventures of the Event Loop

[📺 @ YouTube](https://www.youtube.com/watch?v=u1kqx6AenYw)

## Terminology

* Event queue -- place where JS code is waiting for getting to execute (script tag, DOM event handler, timer event, XHR).
  1. Truly a queue (FIFO), as in "tasks *within* a queue are executed in the order of their arrival".
* Task.
  1. ...is executed without interruptions.
* Rendering pipeline -- part of the browser responsible for painting things in the window.
  1. ...*can* run after a task finishes.
  1. ...runs about each ~16ms (60 fps => 1000ms / 60frames === 16.(6)ms).
  1. ...**can not** run until the task finishes.
  1. ==> the tasks should take less than 16ms to execute, ideally.
* Event loop.
  1. ...can have more than one task queue.
  1. ...queues can be executed in *any order*.
  1. Tasks from the same source go to the same event queue.
* Microtask ~~ Promise.
  * ...has an own microtask queue.
  * ...runs after **EVERY** task.
  * ...rendering pipeline waits for **ALL** the microtasks to complete just like it waits for a regular task.
* Animation Frame Callback Queue (or simply put Animation Queue).
  * ...used via `requestAnimationFrame(() => {...})`.
  * ...has an own queue.
* "check phase" in Node.js.
  

## In Nutshell

### Browser

❗❗❗❗❗TODO

```js
while (true) {
  const queue = getNextQueue();
  const task = queue.pop();
  execute(task);
  
  while (microtaskQueue.hasTasks()) {
    const microtask = microtaskQueue.pop();
    execute(microtask); // CAN enqueue into `microtaskQueue`
  }
  
  if (isRepaintTime()) {
    const animationTasks = [...animationQueue];
    animationTasks.forEach(animationTask =>
      execute(animationTask) // CAN enqueue into `animationQueue`; WILL NOT enqueue into `animationTasks`
    );
  
    repaint();
  }
}
```

### Node.js

* 😄 There are NO script parsing events.
* 😄 No pesky user interactions.
* 😄 No animation frame callbacks.
* 😄 No rendering pipeline event at all.
* Has an event queue for all callbacks (XHR, disk I/O, etc.)
* Queue for timer events (`setTimeout()`, `setImmediate()`, etc.)
* ❗ All next tick callbacks run before any of the promises.
* ⁉️ `setImmediate(...)` vs `process.nextTick(...)`
  > `setImmediate(...)` does something on the next tick
  > 
  > `process.nextTick(...)` does something immediately.
  > 
  > Easy!
  
```js
while (true) {
  const queue = getNextQueue();
  
  while (queue.hasTasks()) {
    const task = queue.pop();
    execute(task);
    
    while (nextTickQueue.hasTasks()) {
      const nextTickTask = nextTickQueue.pop();
      execute(nextTickTask);
    }
    
    while (promiseQueue.hasTasks()) {
      const promiseTask = promiseQueue.pop();
      execute(promiseTask);
    }
  }
}
```

### Web Workers

* 😄 Has OWN event loop.
* 😄 Has OWN stack.
* 😄 Has OWN task queue.
* 😄 There are NO script parsing events.
* 😄 No pesky user interactions.
* 😄 No DOM manipulations

```js
while (true) {
  while (queue.hasTasks()) {
    const task = queue.pop();
    execute(task);
    
    while (promiseQueue.hasTasks()) {
      const promiseTask = promiseQueue.pop();
      execute(promiseTask);
    }
  }
}
```
