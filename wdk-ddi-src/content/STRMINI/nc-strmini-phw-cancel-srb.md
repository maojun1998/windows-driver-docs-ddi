---
UID: NC.strmini.PHW_CANCEL_SRB
title: PHW_CANCEL_SRB
author: windows-driver-content
description: 
ms.assetid: a12b0583-c478-4f55-8420-bc7dd6ec4130
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: strmini.h
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

# PHW_CANCEL_SRB callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PHW_CANCEL_SRB PhwCancelSrb; 

// Definition

VOID PhwCancelSrb 
(
	IN PHW_STREAM_REQUEST_BLOCK SRB
)
{...}

PHW_CANCEL_SRB 


```

## -parameters

### -param SRB: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also