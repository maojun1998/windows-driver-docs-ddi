---
UID: NC.ntddk.PHALMCAINTERFACEUNLOCK
title: PHALMCAINTERFACEUNLOCK
author: windows-driver-content
description: 
ms.assetid: 3f821854-cbf2-454d-81a1-4089dfa39b8e
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.alt-api:
req.alt-loc:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
---

# PHALMCAINTERFACEUNLOCK callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PHALMCAINTERFACEUNLOCK Phalmcainterfaceunlock; 

// Definition

VOID Phalmcainterfaceunlock 
(
	 VOID
)
{...}

PHALMCAINTERFACEUNLOCK 


```

## -parameters

### -param VOID: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also