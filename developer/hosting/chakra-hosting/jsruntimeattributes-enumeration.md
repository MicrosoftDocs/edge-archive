---
description: "Attributes of a runtime. "
title: "JsRuntimeAttributes Enumeration | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsRuntimeAttributes"
helpviewer_keywords: 
  - "JsRuntimeAttributes enumeration"
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsRuntimeAttributes Enumeration

Attributes of a runtime.  
  
## Syntax  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## Members  
  
### Values  
  
|Name|Description|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|The runtime should support reliable script interruption. This increases the number of places where the runtime will check for a script interrupt request at the cost of a small amount of runtime performance.|  
|`JsRuntimeAttributeDisableBackgroundWork`|The runtime will not do any work (such as garbage collection) on background threads.|  
|`JsRuntimeAttributeDisableEval`|Using `eval` or `function` constructor will throw an exception.|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|Runtime will not generate native code.|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|Runtime will enable all experimental features.|  
|`JsRuntimeAttributeEnableIdleProcessing`|Host will call `JsIdle`, so enable idle processing. Otherwise, the runtime will manage memory slightly more aggressively.|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|Calling `JsSetException` will also dispatch the exception to the script debugger (if any) giving the debugger a chance to break on the exception.|  
|`JsRuntimeAttributeNone`|No special attributes.|  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
