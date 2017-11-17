---
UID: NC.wdfio.PFN_WDFIOQUEUEASSIGNFORWARDPROGRESSPOLICY
title: PFN_WDFIOQUEUEASSIGNFORWARDPROGRESSPOLICY
author: windows-driver-content
description: 
ms.assetid: a6691619-1c50-4083-8ee0-58f01df24db0
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdfio.h
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

# PFN_WDFIOQUEUEASSIGNFORWARDPROGRESSPOLICY callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_WDFIOQUEUEASSIGNFORWARDPROGRESSPOLICY PfnWdfioqueueassignforwardprogresspolicy; 

// Definition

WDFAPI PfnWdfioqueueassignforwardprogresspolicy 
(
	PWDF_DRIVER_GLOBALS DriverGlobals
	WDFQUEUE Queue
	PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY ForwardProgressPolicy
)
{...}

PFN_WDFIOQUEUEASSIGNFORWARDPROGRESSPOLICY 


```

## -parameters

### -param DriverGlobals: 
### -param Queue: 
### -param ForwardProgressPolicy: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also