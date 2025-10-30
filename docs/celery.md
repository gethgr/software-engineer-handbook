# ⚙️ Celery Commands Cheat Sheet

> Practical guide for most common and usefull commands for Celery.

---


## 🧩️ Running Celery Workers
```bash
celery -A proj worker --loglevel=info
# Starts a Celery worker for the project `proj` with log level set to info.

celery -A proj worker --loglevel=debug
# Starts a Celery worker for the project `proj` with log level set to debug (more detailed logs).

celery -A proj worker --concurrency=4
# Start the worker with a specific number of concurrent tasks (4 in this case).
```

## 🛠️ Celery Beat Scheduler
```bash
celery -A proj beat --loglevel=info
# Starts the Celery Beat scheduler, which periodically schedules tasks.
```

## 🧮 Utilities & Debugging
``` bash
celery -A proj status
# Display the status of workers.

celery -A proj inspect active
# Show active tasks currently being processed by the workers.

celery -A proj inspect scheduled
# Show scheduled tasks that are about to be executed.

celery -A proj inspect reserved
# Show reserved tasks waiting to be executed.
```

## 🔄 Restarting & Shutting Down Workers
```bash
celery -A proj control shutdown
# Gracefully shuts down all Celery workers.

celery -A proj control restart
# Gracefully restarts all Celery workers.
```


## 🧹 Purging Celery Queues
```bash
celery -A proj result <task_id>
# Retrieve the result of a specific task using its task ID.

celery -A proj revoke <task_id>
# Revoke a specific task by task ID, preventing it from executing.
```

## 🧱 Custom Commands
```bash
celery -A proj flower
# Starts Flower, a real-time web-based monitoring tool for Celery.
```

## 🧯 Worker Supervision (Optional)
```bash
celery -A proj multi start worker1 worker2
# Starts multiple workers with different names (worker1, worker2).

celery -A proj multi stopwait worker1 worker2
# Stops the multiple workers gracefully (waits for them to finish processing current tasks).
```