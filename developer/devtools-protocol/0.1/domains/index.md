---
description: List of references for supported domains in Microsoft Edge DevTools Protocol Version 0.1.
title: DevTools Protocol Domains - DevTools Protocol Version 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.service: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
---
# DevTools Protocol Domains - DevTools Protocol Version 0.1 (EdgeHTML)  

## [Debugger](debugger.md)  

Debugger domain exposes JavaScript debugging capabilities. It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.
## [Page](page.md)
Actions and events related to the inspected page belong to the page domain.
## [Runtime](runtime.md)
Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects. Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference. Original objects are maintained in memory unless they are either explicitly released.
## [Schema](schema.md)
Provides information about the protocol schema.
