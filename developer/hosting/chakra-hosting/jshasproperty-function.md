---
description: "Determines whether an object has a property."
title: "JsHasProperty Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsHasProperty"
helpviewer_keywords: 
  - "JsHasProperty function"
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsHasProperty Function

Determines whether an object has a property.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### Parameters  
 `object`  
 The object that may contain the property.  
  
 `propertyId`  
 The ID of the property.  
  
 `hasProperty`  
 Whether the object (or a prototype) has the property.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
