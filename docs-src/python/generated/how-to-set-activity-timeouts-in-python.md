---
id: how-to-set-activity-timeouts-in-python
title: How to set Activity Timeouts in Python
sidebar_label: Set Activity Timeouts
description: Set Activity timeouts from within your Workflow Definition.
tags:
- activity
- timeout
- python sdk
- code sample
---

<!-- DO NOT EDIT THIS FILE DIRECTLY.
THIS FILE IS GENERATED from https://github.com/temporalio/documentation-samples-python/blob/main/activity_timeouts_retires/your_workflows_dacx.py. -->

Activity options are set as keyword arguments after the Activity arguments.

Available timeouts are:

- schedule_to_close_timeout
- schedule_to_start_timeout
- start_to_close_timeout

<div class="copycode-notice-container"><div class="copycode-notice"><img data-style="copycode-icon" src="/icons/copycode.png" alt="Copy code icon" /> Sample application code information <img id="i-f767fff4-be83-4040-982b-31e5aa0c1a8e" data-event="clickable-copycode-info" data-style="chevron-icon" src="/icons/chevron.png" alt="Chevron icon" /></div><div id="copycode-info-f767fff4-be83-4040-982b-31e5aa0c1a8e" class="copycode-info">The following code sample comes from a working and tested sample application. The code sample might be abridged within the guide to highlight key aspects. Visit the source repository to <a href="https://github.com/temporalio/documentation-samples-python/blob/main/activity_timeouts_retires/your_workflows_dacx.py">view the source code</a> in the context of the rest of the application code.</div></div>

```python
# ...
        activity_timeout_result = await workflow.execute_activity(
            your_activity,
            YourParams(greeting, "Activity Timeout option"),
            # Activity Execution Timeout
            start_to_close_timeout=timedelta(seconds=10),
            # schedule_to_start_timeout=timedelta(seconds=10),
            # schedule_to_close_timeout=timedelta(seconds=10),
        )
```