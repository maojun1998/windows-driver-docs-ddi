---
UID: NC.pep_x.PEPCALLBACKPOWERONCRASHDUMPDEVICE
title: PEPCALLBACKPOWERONCRASHDUMPDEVICE
author: windows-driver-content
description: 
ms.assetid: 318af8eb-3504-4cac-a150-c5e2d4f4e8d0
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: pep_x.h
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

# PEPCALLBACKPOWERONCRASHDUMPDEVICE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PEPCALLBACKPOWERONCRASHDUMPDEVICE Pepcallbackpoweroncrashdumpdevice; 

// Definition

BOOLEAN Pepcallbackpoweroncrashdumpdevice 
(
	PPEP_CRASHDUMP_INFORMATION CrashdumpInformation
)
{...}

PEPCALLBACKPOWERONCRASHDUMPDEVICE PPEPCALLBACKPOWERONCRASHDUMPDEVICE


```

## -parameters

### -param CrashdumpInformation: 



## -returns

Returns BOOLEAN that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also