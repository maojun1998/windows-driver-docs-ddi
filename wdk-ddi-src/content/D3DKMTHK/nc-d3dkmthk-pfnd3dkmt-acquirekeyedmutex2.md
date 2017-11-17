---
UID: NC.d3dkmthk.PFND3DKMT_ACQUIREKEYEDMUTEX2
title: PFND3DKMT_ACQUIREKEYEDMUTEX2
author: windows-driver-content
description: 
ms.assetid: b8185620-23de-4e07-a746-bff27d6314c8
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmthk.h
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

# PFND3DKMT_ACQUIREKEYEDMUTEX2 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3DKMT_ACQUIREKEYEDMUTEX2 Pfnd3dkmtAcquirekeyedmutex2; 

// Definition

NTSTATUS Pfnd3dkmtAcquirekeyedmutex2 
(
	D3DKMT_ACQUIREKEYEDMUTEX2 *
)
{...}

PFND3DKMT_ACQUIREKEYEDMUTEX2 


```

## -parameters

### -param *: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also