---
UID: NF.ucxsstreams.UcxStaticStreamsCreate
title: UcxStaticStreamsCreate function
author: windows-driver-content
description: Creates a static streams object.
old-location: buses\_ucxstaticstreamscreate.htm
old-project: usbref
ms.assetid: F7AA10E3-5F56-4751-A603-54A0BFB00927
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UcxStaticStreamsCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxsstreams.h
req.include-header: Ucxclass.h, Ucxstreams.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: UcxStaticStreamsCreate
req.alt-loc: ucxsstreams.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UcxStaticStreamsCreate function



## -description
Creates a static streams object.


## -syntax

````
NTSTATUS UcxStaticStreamsCreate(
  [in]           UCXENDPOINT            Endpoint,
  [out]          PUCXSSTREAMS_INIT      *SStreamsInit,
  [in, optional] PWDF_OBJECT_ATTRIBUTES Attributes,
  [out]          UCXSSTREAMS            *SStreams
);
````


## -parameters

### -param Endpoint [in]

A handle to the endpoint object that supports static streams. The client driver retrieved the handle in a previous call to <a href="buses._ucxendpointcreate">UcxEndpointCreate</a>.

### -param SStreamsInit [out]

A pointer to a <b>UCXSSTREAMS_INIT</b> structure that describes various configuration
        operations for creating the stream object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.

### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the stream object. 

### -param SStreams [out]

A pointer to a variable that receives a handle to the new stream object.

## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 

## -remarks
The client driver for the host controller must call this method after the <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a> call. The parent of the new endpoint object is the endpoint object. 

Typically, the client driver calls this method in its implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> event callback. 

## -requirements
<table>
<tr>
<th width="30%">
Minimum support
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxsstreams.h (include Ucxclass.h or Ucxstreams.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>