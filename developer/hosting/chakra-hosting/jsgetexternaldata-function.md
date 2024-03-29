---
description: "Retrieves the data from an external object."
title: "JsGetExternalData Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsGetExternalData"
helpviewer_keywords: 
  - "JsGetExternalData function"
ms.assetid: 1919e1da-3ea7-4269-a5fb-a3be06bd029b
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsGetExternalData Function

Retrieves the data from an external object.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExternalData(  
   _In_ JsValueRef object,  
   _Out_ void **externalData  
);  
```  
  
#### Parameters  
 `object`  
 The external object.  
  
 `externalData`  
 The external data stored in the object. Can be null if no external data is stored in the object.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
