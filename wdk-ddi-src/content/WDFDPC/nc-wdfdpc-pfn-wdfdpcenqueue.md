---
UID: NC.wdfdpc.PFN_WDFDPCENQUEUE
title: PFN_WDFDPCENQUEUE
author: windows-driver-content
description: 
ms.assetid: b1699748-cfe4-47be-b687-c80e068dc0ab
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdfdpc.h
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

# PFN_WDFDPCENQUEUE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_WDFDPCENQUEUE PfnWdfdpcenqueue; 

// Definition

WDFAPI PfnWdfdpcenqueue 
(
	PWDF_DRIVER_GLOBALS DriverGlobals
	WDFDPC Dpc
)
{...}

PFN_WDFDPCENQUEUE 


```

## -parameters

### -param DriverGlobals: 
### -param Dpc: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also