---
description: "Tests whether an object has a value at the specified index."
title: "JsHasIndexedProperty Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsHasIndexedProperty"
helpviewer_keywords: 
  - "JsHasIndexedProperty function"
ms.assetid: 30436a3d-fda0-407e-aba2-142be2310372
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsHasIndexedProperty Function

Tests whether an object has a value at the specified index.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ bool *result  
);  
```  
  
#### Parameters  
 `object`  
 The object to operate on.  
  
 `index`  
 The index to test.  
  
 `result`  
 Whether the object has an value at the specified index.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
