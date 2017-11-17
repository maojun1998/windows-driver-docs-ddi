---
UID: NC.wdm.PFN_NT_OPEN_TRANSACTION
title: PFN_NT_OPEN_TRANSACTION
author: windows-driver-content
description: 
ms.assetid: 4668abf4-c21b-4715-9e98-8750f139f80a
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdm.h
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

# PFN_NT_OPEN_TRANSACTION callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_NT_OPEN_TRANSACTION PfnNtOpenTransaction; 

// Definition

NTSTATUS PfnNtOpenTransaction 
(
	PHANDLE TransactionHandle
	ACCESS_MASK DesiredAccess
	POBJECT_ATTRIBUTES ObjectAttributes
	LPGUID Uow
	HANDLE TmHandle
)
{...}

PFN_NT_OPEN_TRANSACTION 


```

## -parameters

### -param TransactionHandle: 
### -param DesiredAccess: 
### -param ObjectAttributes: 
### -param Uow: 
### -param TmHandle: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also