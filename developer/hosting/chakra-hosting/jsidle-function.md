---
description: "Tells the runtime to do any idle processing it need to do."
title: "JsIdle Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsIdle"
helpviewer_keywords: 
  - "JsIdle function"
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsIdle Function

Tells the runtime to do any idle processing it need to do.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### Parameters  
 `nextIdleTick`  
 The next system tick when there will be more idle work to do. Can be null. Returns the maximum number of ticks if there no upcoming idle work to do.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 If idle processing has been enabled for the current runtime, calling `JsIdle` will inform the current runtime that the host is idle and that the runtime can perform memory cleanup tasks.  
  
 `JsIdle` can also return the number of system ticks until there will be more idle work for the runtime to do. Calling `JsIdle` before this number of ticks has passed will do no work.  
  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
