---
UID: NC:swenum.PFNQUERYREFERENCESTRING
title: PFNQUERYREFERENCESTRING
author: windows-driver-content
description: This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool.
old-location: stream\kstrqueryreferencestring.htm
old-project: stream
ms.assetid: 08fd750f-19cc-4d78-a26b-9f790c5c3acf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.kstrqueryreferencestring, KStrQueryReferenceString routine [Streaming Media Devices], KStrQueryReferenceString, PFNQUERYREFERENCESTRING, PFNQUERYREFERENCESTRING, ks/KStrQueryReferenceString, ksfunc_ce750f42-efeb-4861-b451-ef0f8be40f9a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: swenum.h
req.include-header: Ks.h, Swenum.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	KStrQueryReferenceString
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE"
req.product: Windows 10 or later.
---


# PFNQUERYREFERENCESTRING callback function
This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>.

## Syntax

```
PFNQUERYREFERENCESTRING Pfnqueryreferencestring;

NTSTATUS Pfnqueryreferencestring(
  PVOID Context,
  PWCHAR *String
)
{...}
```

## Parameters

`Context`

Pointer to a device extension of the device's PDO.

`*String`

Pointer to a string containing the reference string associated with the PDO.


## Return Value

None.

## Remarks

The driver can access this method through the <b>QueryReferenceString</b> member of the <a href="..\ks\ns-ks-bus_interface_reference.md">BUS_INTERFACE_REFERENCE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | swenum.h (include Ks.h, Swenum.h) |