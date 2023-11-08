---
id: how-to-define-workflow-parameters-in-go
title: How to define Workflow parameters in Go
sidebar_label: Workflow parameters
description: A Go-based Workflow Definition must accept workflow.Context and may support multiple custom parameters.
tags:
- go sdk
- code sample
- workflow
---

<!-- DO NOT EDIT THIS FILE DIRECTLY.
THIS FILE IS GENERATED from https://github.com/temporalio/documentation-samples-go/blob/main/yourapp/your_workflow_definition_dacx.go. -->

The first parameter of a Go-based Workflow Definition must be of the [`workflow.Context`](https://pkg.go.dev/go.temporal.io/sdk/workflow#Context) type.
It is used by the Temporal Go SDK to pass around Workflow Execution context, and virtually all the Go SDK APIs that are callable from the Workflow require it.
It is acquired from the [`go.temporal.io/sdk/workflow`](https://pkg.go.dev/go.temporal.io/sdk/workflow) package.

The `workflow.Context` entity operates similarly to the standard `context.Context` entity provided by Go.
The only difference between `workflow.Context` and `context.Context` is that the `Done()` function, provided by `workflow.Context`, returns `workflow.Channel` instead of the standard Go `chan`.

Additional parameters can be passed to the Workflow when it is invoked.
A Workflow Definition may support multiple custom parameters, or none.
These parameters can be regular type variables or safe pointers.
However, the best practice is to pass a single parameter that is of a `struct` type, so there can be some backward compatibility if new parameters are added.

All Workflow Definition parameters must be serializable and can't be channels, functions, variadic, or unsafe pointers.

<div class="copycode-notice-container"><div class="copycode-notice"><img data-style="copycode-icon" src="/icons/copycode.png" alt="Copy code icon" /> Sample application code information <img id="i-a610e8d5-de78-4a62-94f9-6c96f825e1d5" data-event="clickable-copycode-info" data-style="chevron-icon" src="/icons/chevron.png" alt="Chevron icon" /></div><div id="copycode-info-a610e8d5-de78-4a62-94f9-6c96f825e1d5" class="copycode-info">The following code sample comes from a working and tested sample application. The code sample might be abridged within the guide to highlight key aspects. Visit the source repository to <a href="https://github.com/temporalio/documentation-samples-go/blob/main/yourapp/your_workflow_definition_dacx.go">view the source code</a> in the context of the rest of the application code.</div></div>

```go
package yourapp

import (
	"time"

	"go.temporal.io/sdk/workflow"
)


// YourWorkflowParam is the object passed to the Workflow.
type YourWorkflowParam struct {
	WorkflowParamX string
	WorkflowParamY int
}
// ...
// YourWorkflowDefinition is your custom Workflow Definition.
func YourWorkflowDefinition(ctx workflow.Context, param YourWorkflowParam) (*YourWorkflowResultObject, error) {
// ...
}
```