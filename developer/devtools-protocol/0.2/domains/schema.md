---
description: DevTools Protocol Version 0.2 (EdgeHTML) reference for the Schema Domain. Provides information about the protocol schema.
title: Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.service: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
---
# Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)  

Provides information about the protocol schema.  

| Classification | Members |  
|:--- |:--- |  
| [Methods](#methods) | [getDomains](#getdomains) |  
| [Types](#types) | [Domain object](#domain) |  

## Methods  

### getDomains  

Returns supported domains.  

| Returns | Type | Details |  
|:--- |:--- |:--- |  
| domains | [Domain[]](#domain) | List of supported domains. |  

---  

## Types  

### Domain object  

<a name="domain"></a>  

Description of the protocol domain.  

| Properties | Type | Details |  
|:--- |:--- |:--- |  
| name | `string` | Domain name. |  
| version | `string` | Domain version. |  

---  
