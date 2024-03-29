---
description: "Retrieves the string pointer of a string value."
title: "JsStringToPointer Function | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsStringToPointer"
helpviewer_keywords: 
  - "JsStringToPointer function"
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsStringToPointer Function

Retrieves the string pointer of a string value.  
  
## Syntax  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### Parameters  
 `value`  
 The string value to convert to a string pointer.  
  
 `stringValue`  
 The string pointer.  
  
 `stringLength`  
 The length of the string.  
  
## Return Value  
 The code `JsNoError` if the operation succeeded, a failure code otherwise.  
  
## Remarks  
 This function retrieves the string pointer of a string value. It will fail with `JsErrorInvalidArgument` if the type of the value is not string. The lifetime of the string returned will be the same as the lifetime of the value it came from, however the string pointer is not considered a reference to the value (and so will not keep it from being collected).  
  
 Requires an active script context.  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
