---
description: "Suspends script execution and terminates any running scripts in a runtime."
title: "JsDisableRuntimeExecution Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsDisableRuntimeExecution"
helpviewer_keywords: 
  - "JsDisableRuntimeExecution function"
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsDisableRuntimeExecution Function

Suspends script execution and terminates any running scripts in a runtime.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### Parameters  
 `runtime`  
 The runtime to be suspended.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 Calls to a suspended runtime will fail until `JsEnableRuntimeExecution` is called.  
  
 This API does not have to be called on the thread the runtime is active on. Although the runtime will be set into a suspended state, an executing script may not be suspended immediately; a running script will be terminated with an uncatchable exception as soon as possible.  
  
 Suspending execution in a runtime that is already suspended is a no-op.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
