---
description: DevTools Protocol Version 0.2 (EdgeHTML) reference for the Runtime Domain. Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects. Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference. Original objects are maintained in memory unless they are either explicitly released.
title: Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.service: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
---
# Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)  

Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects. Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference. Original objects are maintained in memory unless they are either explicitly released.  

| Classification | Members |  
|:--- |:--- |  
| [**Methods**](#methods) | [enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries) |  
| [**Events**](#events) | [executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled) |  
| [**Types**](#types) | [ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace) |  

## Methods  

### enable  

Enables reporting of the `executionContextCreated`, `executionContextDestroyed`, and `executionContextsCleared` events.  When the reporting gets enabled the `executionContextCreated` event will be sent immediately for each existing execution context.  

---  

### disable  

Disables reporting of the `executionContextCreated`, `executionContextDestroyed`, and `executionContextsCleared` events.  

---  

### evaluate  

Evaluates expression on global object.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| expression | `string` | Expression to evaluate. |  
| includeCommandLineAPI \(optional\) | `boolean` | Determines whether Command Line API should be available during the evaluation. |  
| objectGroup \(optional\) | `string` | Symbolic group name that can be used to release multiple objects. |  
| silent \(optional\) | `boolean` | In silent mode exceptions thrown during evaluation are not reported and do not pause execution.  Overrides `setPauseOnException` state. |  
| contextId \(optional\) | [ExecutionContextId](#executioncontextid) | Specifies in which execution context to perform evaluation.  If the parameter is omitted the evaluation will be performed in the context of the inspected page. |  
| returnByValue \(optional\) | `boolean` | Whether the result is expected to be a JSON object that should be sent by value. |  
| awaitPromise \(optional\) | `boolean` | Whether execution should `await` for resulting value and return once awaited promise is resolved. |  

| Returns | Type | Details |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | Evaluation result. |  

---  

### callFunctionOn  

Calls function with given declaration on the given object.  Object group of the result is inherited from the target object.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| functionDeclaration | `string` | Declaration of the function to call. |  
| objectId \(optional\) | [RemoteObjectId](#remoteobjectid) | Identifier of the object to call function on.  Either `objectId` or `executionContextId` should be specified.  `objectId` must be from the `Runtime.evaluate()` function. |  
| arguments \(optional\) | [CallArgument[]](#callargument) | Call arguments.  All call arguments must belong to the same JavaScript world as the target object. |  
| boolean \(optional\) | `boolean` | In silent mode exceptions thrown during evaluation are not reported and do not pause execution. Overrides `setPauseOnException` state. |  
| returnByValue \(optional\) | `boolean` | Whether the result is expected to be a JSON object which should be sent by value. |  
| awaitPromise \(optional\) | `boolean` | Whether execution should `await` for resulting value and return once awaited promise is resolved. |  
| executionContextId \(optional\) | [ExecutionContextId](#executioncontextid) | Specifies execution context which global object will be used to call function on.  Either
`executionContextId` or `objectId` should be specified |  
| objectGroup \(optional\) | `string` | Symbolic group name that can be used to release multiple objects.  If `objectGroup` is not specified and `objectId` is, `objectGroup` will be inherited from object. |  

| Returns | Type | Details |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | Call result. |  

---  

### awaitPromise  

Add handler to promise with given promise object id.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| promiseObjectId | [RemoteObjectId](#remoteobjectid) | Identifier of the promise. |  
| returnByValue \(optional\) | boolean | Whether the result is expected to be a JSON object that should be sent by value. |  

| Returns | Type | Details |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | Promise result.  Will contain rejected value if promise was rejected. |  

---  

### getProperties  

Returns properties of a given object. Object group of the result is inherited from the target object.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| objectId | [RemoteObjectId](#remoteobjectid) | Identifier of the object to return properties for.  `objectId` must be from the `Debugger.evaluateOnCallFrame()` function. |  
| ownProperties \(optional\) | `boolean` | If `true`, returns properties belonging only to the element itself, not to its prototype chain. |  
| accessorPropertiesOnly \(optional\) | `boolean` | **Experimental**.  If `true`, returns accessor properties \(with getter/setter\) only; internal properties are not returned either. |  

| Returns | Type | Details |  
|:--- |:--- |:--- |  
| result | [PropertyDescriptor[]](#propertydescriptor) | Object properties. |  

---  

### globalLexicalScopeNames  

Returns all let, const, and class variables from the console global scope.  

| Returns | Type | Details |  
|:--- |:--- |:--- |  
| names | `string[]` | &nbsp; |  

---  

### releaseObject  

Releases remote object with given ID.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| objectId | [RemoteObjectId](#remoteobjectid) | Identifier of the object to release. |  

---  

### releaseObjectGroup  

Releases all remote objects that belong to a given group.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| objectGroup | `string` | Symbolic object group name. |  

---  

### discardConsoleEntries  

Discards collected exceptions and console API calls.  

---  

## Events  

### executionContextCreated  

Issued when new execution context is created.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| context | [ExecutionContextDescription](#executioncontextdescription) | A newly created execution context. |  

---  

### executionContextDestroyed  

Issued when execution context is destroyed.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| executionContextId | [ExecutionContextId](#executioncontextid) | ID of the destroyed context. |  

---  

### executionContextsCleared  

Issued when all executionContexts were cleared in browser.  

&nbsp;  

---  

### exceptionThrown  

Issued when exception was thrown and unhandled.  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| timestamp | [Timestamp](#timestamp) | Timestamp of the exception. |  
| exceptionDetails | [ExceptionDetails](#exceptiondetails) | &nbsp; |  

---  

### consoleAPICalled  

| Parameters | Type | Details |  
|:--- |:--- |:--- |  
| type | `string` | Type of the call.  Allowed values:  `log`, `info`, `warning`, `error`, `debug`, `assert`, `table`, `trace`, `dir`, `dirxml`, `clear`, `select`, `count`, `countReset`, `timeEnd`, `timeStamp`, `startGroup`, `startGroupCollapsed`, and `endGroup` |  
| args | [RemoteObject[]](#remoteobject | Call arguments. |  
| executionContextId | [ExecutionContextId](#executioncontextid) | Identifier of the context where console call was made. |  
| timestamp \(optional\) | [Timestamp](#timestamp) | Call timestamp. |  
| stackTrace \(optional\) | [StackTrace](#stacktrace) | Stack trace captured if available. |  

---  

## Types  

### ScriptId string  

<a name="scriptid"></a>

Unique script identifier.  

&nbsp;  

---  

### RemoteObjectId string  

<a name="remoteobjectid"></a>

Unique object identifier.  

&nbsp;  

---  

### UnserializableValue string  

<a name="unserializablevalue"></a>  

Primitive value which cannot be JSON-stringified.  

##### Allowed Values  

`Infinity`, `NaN`, `-Infinity`, `-0`  

---  

### RemoteObject object  

<a name="remoteobject"></a>  

Mirror object referencing original JavaScript object.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| type | `string` | Object type.  Allowed values:  `object`, `function`, `undefined`, `string`, `number`, `boolean`, and `symbol` |  
| subtype \(optional\) | `string` | Object subtype hint.  Specified for `object` type values only.  Allowed values:  `null`, `error`, `promise`, and `node` |  
| className \(optional\) | `string` | Object class \(constructor\) name.  Specified for `object` type values only. |  
| value \(optional\) | `any` | Remote object value in case of primitive values or JSON values \(if it was requested\). |  
| unserializableValue \(optional\) | [UnserializableValue](#unserializablevalue) | Primitive value which can not be JSON-stringified does not have `value`, but gets this property. |  
| description \(optional\) | `string` | String representation of the object. |  
| objectId \(optional\) | [RemoteObjectId](#remoteobjectid) | Unique object identifier \(for non-primitive values\). |  
| msDebuggerPropertyId \(optional\) | `string` | **Experimental**.  Microsoft:  The associated debugger property ID for this object. |  

---  

### PropertyDescriptor object  

<a name="propertydescriptor"></a>  

Object property descriptor.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| name | `string` | Property name or symbol description. |  
| value \(optional\) | [RemoteObject](#remoteobject) | The value associated with the property. |  
| writable \(optional\) | `boolean` | `True` if the value associated with the property may be changed \(data descriptors only\). |  
| get \(optional\) | [RemoteObject](#remoteobject) | A function which serves as a getter for the property, or `undefined` if there is no getter \(accessor descriptors only\). |  
| set \(optional\) | [RemoteObject](#remoteobject) | A function which serves as a setter for the property, or `undefined` if there is no setter \(accessor descriptors only\). |  
| configurable | `boolean` | `True` if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object. |  
| enumerable | `boolean` | `True` if this property shows up during enumeration of the properties on the corresponding object. |  
| wasThrown \(optional\) | `boolean` | `True` if the result was thrown during the evaluation. |  
| isOwn \(optional\) | `boolean` | `True` if the property is owned for the object. |  
| msReturnValue \(optional\) | `boolean` | **Experimental**.  Microsoft:  `True` if the property is a return value. |  
| symbol \(optional\) | [RemoteObject](#remoteobject) | Property symbol object, if the property is of the `symbol` type. |  

---  

### CallArgument object  

<a name="callargument"></a>  

Represents function call argument.  Either remote object ID `objectId`, primitive `value`, unserializable primitive value, or neither of \(for undefined\) them should be specified.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| value \(optional\) | `any` | Primitive value or serializable javascript object. |  
| unserializableValue \(optional\) | [UnserializableValue](#unserializablevalue) | Primitive value which can not be JSON-stringified. |  
| objectId \(optional\) | [RemoteObjectId](#remoteobjectid)] | Remote object handle. |  

---  

### ExecutionContextId integer  

<a name="executioncontextid"></a>  

ID of an execution context.  

&nbsp;  

---  

### ExecutionContextDescription object  

<a name="executioncontextdescription"></a>  

Description of an isolated world.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| id | [ExecutionContextId](#executioncontextid) | Unique ID of the execution context.  It can be used to specify in which execution context
script evaluation should be performed. |  
| origin | `string` | Execution context origin. |  
| name | `string` | Human readable name describing given context. |  

---  

### ExceptionDetails object  

<a name="exceptiondetails"></a>  

Detailed information about exception (or error) that was thrown during script compilation or execution.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| exceptionId | `integer` | Exception ID. |  
| text | `string` | Exception text, which should be used together with exception object when available. |  
| lineNumber | `integer` | Line number of the exception location \(0-based\). |  
| columnNumber | `integer` | Column number of the exception location \(0-based\). |  
| scriptId \(optional\) | [ScriptId](#scriptid) | Script ID of the exception location. |  
| url \(optional\) | `string` | URL of the exception location, to be used when the script was not reported. |  
| stackTrace \(optional\) | [StackTrace](#stacktrace) | JavaScript stack trace if available. |  
| exception \(optional\) | [RemoteObject](#remoteobject) | Exception object if available. |  
| executionContextId \(optional\) | [ExecutionContextId](#executioncontextid) | Identifier of the context where exception happened. |  

---  

### Timestamp integer  

<a name="timestamp"></a>  

Number of milliseconds since epoch.  

&nbsp;  

---  

### CallFrame object  

<a name="callframe"></a>  

Stack entry for runtime errors and assertions.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| functionName | `string` | JavaScript function name. |  
| scriptId | [ScriptId](#scriptid) | JavaScript script id. ScriptId will be empty if debugger is not enabled. |  
| url | `string` | JavaScript script name or url. |  
| lineNumber | `integer` | JavaScript script line number \(0-based\). |  
| columnNumber | integer | JavaScript script column number \(0-based\). |  

---  

### StackTrace object  

<a name="stacktrace"></a>  

Call frames for assertions or error messages.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| description \(optional\) | `string` | String label of this stack trace.  For async traces this may be a name of the function that initiated the async call. |  
| callFrames | [CallFrame[]](#callframe) | JavaScript function name. |  
| parent \(optional\) | [StackTrace](#stacktrace) | Asynchronous JavaScript stack trace that preceded this stack, if available. |  

---  
