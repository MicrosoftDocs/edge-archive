---
description: "The JavaScript type of a JsValueRef."
title: "JsValueType Enumeration | Microsoft Docs"
ms.service: microsoft-edge
ms.topic: "reference"
f1_keywords: 
  - "jsrt/JsValueType"
helpviewer_keywords: 
  - "JsValueType enumeration"
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: "MSEdgeTeam"
ms.author: "msedgedevrel"
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# JsValueType Enumeration

The JavaScript type of a JsValueRef.  
  
## Syntax  
  
```cpp  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## Members  
  
### Values  
  
|Name|Description|  
|----------|-----------------|  
|`JsUndefined`|The value is the `undefined` value.|  
|`JsNull`|The value is the `null` value.|  
|`JsNumber`|The value is a JavaScript number value.|  
|`JsString`|The value is a JavaScript string value.|  
|`JsBoolean`|The value is a JavaScript Boolean value.|  
|`JsObject`|The value is a JavaScript object value.|  
|`JsFunction`|The value is a JavaScript function object value.|  
|`JsError`|The value is a JavaScript error object value.|  
|`JsArray`|The value is a JavaScript array object value.|  
|`JsSymbol`|The value is a JavaScript symbol value.<br /><br /> This enumeration value is supported only in Microsoft Edge mode.|  
|`JsArrayBuffer`|The value is a JavaScript `ArrayBuffer` object value.<br /><br /> This enumeration value is supported only in Microsoft Edge mode.|  
|`JsTypedArray`|The value is a JavaScript typed array object value.<br /><br /> This enumeration value is supported only in Microsoft Edge mode.|  
|`JsDataView`|The value is a JavaScript `DataView` object value.<br /><br /> This enumeration value is supported only in Microsoft Edge mode.|  
  
## Requirements  
 **Header:** jsrt.h  
  
## See Also  
 [Reference (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
