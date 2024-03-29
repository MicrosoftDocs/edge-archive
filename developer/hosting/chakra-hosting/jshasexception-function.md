---
description: "Determines whether the runtime of the current context is in an exception state."
title: "JsHasException Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsHasException"
helpviewer_keywords: 
  - "JsHasException function"
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsHasException Function

Determines whether the runtime of the current context is in an exception state.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### Parameters  
 `hasException`  
 Whether the runtime of the current context is in the exception state.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 If a call into the runtime results in an exception (either as the result of running a script or due to something like a conversion failure), the runtime is placed into an "exception state." All calls into any context created by the runtime (except for the exception APIs) will fail with `JsErrorInExceptionState` until the exception is cleared.  
  
 If the runtime of the current context is in the exception state when a callback returns into the engine, the engine will automatically rethrow the exception.  
  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
