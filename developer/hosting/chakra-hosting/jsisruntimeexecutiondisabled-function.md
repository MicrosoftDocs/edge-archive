---
description: "Returns a value that indicates whether script execution is disabled in the runtime."
title: "JsIsRuntimeExecutionDisabled Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsIsRuntimeExecutionDisabled"
helpviewer_keywords: 
  - "JsIsRuntimeExecutionDisabled function"
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsIsRuntimeExecutionDisabled Function

Returns a value that indicates whether script execution is disabled in the runtime.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### Parameters  
 `runtime`  
 Specifies the runtime to check if execution is disabled.  
  
 `isDisabled`  
 `true` if execution is disabled, `false` otherwise.  
  
## Return Value  
 `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
