---
UID: NC.wdffileobject.PFN_WDFFILEOBJECTGETRELATEDFILEOBJECT
title: PFN_WDFFILEOBJECTGETRELATEDFILEOBJECT
author: windows-driver-content
description: 
ms.assetid: 0b4c4d3d-20b1-4491-80e1-77e88a956969
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdffileobject.h
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

# PFN_WDFFILEOBJECTGETRELATEDFILEOBJECT callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_WDFFILEOBJECTGETRELATEDFILEOBJECT PfnWdffileobjectgetrelatedfileobject; 

// Definition

WDFAPI PfnWdffileobjectgetrelatedfileobject 
(
	PWDF_DRIVER_GLOBALS DriverGlobals
	WDFFILEOBJECT FileObject
)
{...}

PFN_WDFFILEOBJECTGETRELATEDFILEOBJECT 


```

## -parameters

### -param DriverGlobals: 
### -param FileObject: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also