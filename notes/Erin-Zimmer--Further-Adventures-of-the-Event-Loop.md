# Erin Zimmer: Further Adventures of the Event Loop

[📺 @ YouTube](https://www.youtube.com/watch?v=u1kqx6AenYw)

## Terminology

* Event loop.
* Event queue -- place where JS code is waiting for getting to execute (script tag, DOM event handler, timer event, XHR).
* Task.
* Microtask ≅ Promise.
* Animation Frame Callback Queue (aka Animation Queue).
* Rendering pipeline -- part of the browser responsible for painting things in the window.

## Related

* [Phases in Node.js](https://medium.freecodecamp.org/walking-inside-nodejs-event-loop-85caeca391a9)

## In Nutshell

### Browser

* Event loop.
  * runs continuously and is responsible for executing tasks.
  * 😄 can have more than one task queue.
  * 😄 can process a task from any queue. In other words, queues are executed in arbitrary order.
* Task queue.
  * 😄 is a FIFO queue with task entries. I.e. the tasks within the queue are executed in order of their appearance.
  * 😄 tasks from the same source go to the same queue.
  * 😄 when a task is executed, there are no interruptions. 
* Microtask queue (Promise and alike).
  * is separate from regular task queues.
  * runs after **EACH AND EVERY** task.
* Animation queue.
  * is separate from regular task queues and from microtask queue.
  * is used via `requestAnimationFrame(() => {...})`.
* Rendering pipeline.
  * 😞 **CAN NOT RUN** until the task and **ALL** the microtasks and **ALL THE COPIED** animation tasks are complete.
  * **MAY** run after aforementioned tasks are complete. In fact, it runs about each `16ms` (`60`fps => `1000`ms / `60`frames === `16.(6)`ms).
  * therefore, requires tasks & microtasks to be lightweight (under `16`ms in total) and not flooding the tasks and/or microtasks queues.

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
