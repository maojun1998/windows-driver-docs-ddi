---
UID: NC.mrx.PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
title: PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
author: windows-driver-content
description: 
ms.assetid: 56cd56df-e9ad-434b-b156-14bd926a1b2e
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: mrx.h
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

# PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PMRX_CHANGE_BUFFERING_STATE_CALLDOWN PmrxChangeBufferingStateCalldown; 

// Definition

NTSTATUS PmrxChangeBufferingStateCalldown 
(
	IN OUT PRX_CONTEXT RxContext
	IN OUT PMRX_SRV_OPEN SrvOpen
	IN PVOID MRxContext
)
{...}

PMRX_CHANGE_BUFFERING_STATE_CALLDOWN 


```

## -parameters

### -param RxContext: 
### -param SrvOpen: 
### -param MRxContext: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also