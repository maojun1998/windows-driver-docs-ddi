---
UID: NC.wdbgexts.PWINDBG_GET_SYMBOL32
title: PWINDBG_GET_SYMBOL32
author: windows-driver-content
description: 
ms.assetid: a6e679d0-b5d7-4fde-9dc6-775c2cd2dfe0
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdbgexts.h
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

# PWINDBG_GET_SYMBOL32 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PWINDBG_GET_SYMBOL32 PwindbgGetSymbol32; 

// Definition

VOID PwindbgGetSymbol32 
(
	ULONG offset
	PCHAR pchBuffer
	PULONG pDisplacement
)
{...}

PWINDBG_GET_SYMBOL32 


```

## -parameters

### -param offset: 
### -param pchBuffer: 
### -param pDisplacement: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also