---
UID: NC.dsm.DSM_CATEGORIZE_REQUEST
title: DSM_CATEGORIZE_REQUEST
author: windows-driver-content
description: 
ms.assetid: d96f6f3d-b506-46ad-9b42-fedaaebbb751
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dsm.h
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

# DSM_CATEGORIZE_REQUEST callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DSM_CATEGORIZE_REQUEST DsmCategorizeRequest; 

// Definition

ULONG DsmCategorizeRequest 
(
	IN PVOID DsmContext
	IN PDSM_IDS DsmIds
	IN PIRP Irp
	IN PSCSI_REQUEST_BLOCK Srb
	IN PVOID CurrentPath
	OUT PVOID *PathId
	OUT NTSTATUS *Status
)
{...}

DSM_CATEGORIZE_REQUEST 


```

## -parameters

### -param DsmContext: 
### -param DsmIds: 
### -param Irp: 
### -param Srb: 
### -param CurrentPath: 
### -param *PathId: 
### -param *Status: 



## -returns

Returns ULONG that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also