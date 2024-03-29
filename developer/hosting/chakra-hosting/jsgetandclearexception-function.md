---
description: "Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime."
title: "JsGetAndClearException Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetAndClearException"
helpviewer_keywords: 
  - "JsGetAndClearException function"
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsGetAndClearException Function

Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### Parameters  
 `exception`  
 The exception for the runtime of the current context.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 If the runtime of the current context is not in an exception state, this API will return `JsErrorInvalidArgument`. If the runtime is disabled, this will return an exception indicating that the script was terminated, but it will not clear the exception (the exception will be cleared if the runtime is re-enabled using `JsEnableRuntimeExecution`).  
  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
