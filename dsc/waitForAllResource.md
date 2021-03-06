---
title:   DSC WaitForAll Resource
ms.date:  2017-04-07
keywords:  powershell,DSC
description:  
ms.topic:  article
author:  eslesar
manager:  carmonmills
ms.prod:  powershell
---

# DSC WaitForAll Resource

> Applies To: Windows PowerShell 5.0 and later

The **WaitForAll** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](configurations.md)
to specify dependencies on configurations on other nodes.

This resource succeeds if if the resource specified by the **ResourceName** property is in the desired state on all target nodes defined in the **NodeName** property.


## Syntax

```
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ] 
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## Properties

|  Property  |  Description   | 
|---|---| 
| ResourceName| The resource name to depend on.| 
| NodeName| The target nodes of the resource to depend on.| 
| RetryIntervalSec| The number of seconds before retrying. Minimum is 1.| 
| RetryCount| The maximum number of times to retry.| 
| ThrottleLimit| Number of machines to connect simultaneously. Default is new-cimsession default.| 
| DependsOn | Indicates that the configuration of another resource must run before this resource is configured. For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.|


## Example

For an example of how to use this resource, see [Specifying cross-node dependencies](crossNodeDependencies.md)
