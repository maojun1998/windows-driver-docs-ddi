---
UID: NC.bthsdpddi.PAPPENDNODETOCONTAINERNODE
title: PAPPENDNODETOCONTAINERNODE
author: windows-driver-content
description: 
ms.assetid: e1dd6d16-294f-4170-9034-d0f37d3a7a4d
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: bthsdpddi.h
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

# PAPPENDNODETOCONTAINERNODE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PAPPENDNODETOCONTAINERNODE Pappendnodetocontainernode; 

// Definition

NTSTATUS Pappendnodetocontainernode 
(
	PSDP_NODE Container
	__drv_aliasesMem PSDP_NODE Node
)
{...}

PAPPENDNODETOCONTAINERNODE 


```

## -parameters

### -param Container: 
### -param Node: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also