---
UID: NC.dispmprt.DXGKDDI_QUERY_CHILD_STATUS
title: DXGKDDI_QUERY_CHILD_STATUS
author: windows-driver-content
description: 
ms.assetid: f81381e5-bd40-4f1a-b827-288c27178ff6
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dispmprt.h
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

# DXGKDDI_QUERY_CHILD_STATUS callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGKDDI_QUERY_CHILD_STATUS DxgkddiQueryChildStatus; 

// Definition

NTSTATUS DxgkddiQueryChildStatus 
(
	IN_CONST_PVOID MiniportDeviceContext
	INOUT_PDXGK_CHILD_STATUS ChildStatus
	IN_BOOLEAN NonDestructiveOnly
)
{...}

DXGKDDI_QUERY_CHILD_STATUS PDXGKDDI_QUERY_CHILD_STATUS


```

## -parameters

### -param MiniportDeviceContext: 
### -param ChildStatus: 
### -param NonDestructiveOnly: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also