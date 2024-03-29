---
description: "Converts the value to number using standard JavaScript semantics."
title: "JsConvertValueToNumber Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsConvertValueToNumber"
helpviewer_keywords: 
  - "JsConvertValueToNumber function"
ms.assetid: c47b8653-0591-4863-b8b5-33187b315816
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsConvertValueToNumber Function

Converts the value to number using standard JavaScript semantics.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToNumber(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *numberValue  
);  
```  
  
#### Parameters  
 `value`  
 The value to be converted.  
  
 `numberValue`  
 The converted value.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
