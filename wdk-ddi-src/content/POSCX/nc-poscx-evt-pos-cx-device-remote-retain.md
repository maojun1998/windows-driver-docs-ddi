---
UID: NC.poscx.EVT_POS_CX_DEVICE_REMOTE_RETAIN
title: EVT_POS_CX_DEVICE_REMOTE_RETAIN
author: windows-driver-content
description: The EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim on a network device and allows the driver to do additional work.
old-location: pos\evt_pos_cx_device_remote_retain.htm
ms.assetid: 9B23DB23-D995-4737-9302-872F2144823D
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: pos
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtPosCxDeviceRemoteRetain
req.alt-loc: poscx.h
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
ms.keywords: PCSTREAMRESOURCE_DESCRIPTOR, PCSTREAMRESOURCE_DESCRIPTOR, *PPCSTREAMRESOURCE_DESCRIPTOR
req.iface: 
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_REMOTE_RETAIN callback



## -description
<p>The 
  EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim
on a network device and allows the driver to do additional work. This callback is typically only used with network connected devices that require additional logic for handling ownership transitions.</p>


## -prototype

````
EVT_POS_CX_DEVICE_REMOTE_RETAIN EvtPosCxDeviceRemoteRetain;

NTSTATUS EvtPosCxDeviceRemoteRetain(
  _In_ WDFDEVICE device,
  _In_ ULONG     deviceInterfaceTag
)
{ ... }
````


## -parameters
<dl>

### -param <i>device</i> [in]

<dd>
<p>A handle to a framework device object that represents the device.</p>
</dd>

### -param <i>deviceInterfaceTag</i> [in]

<dd>
<p>An identifier used to specify which interface is being retained in a multi-function device.  For a single-interface device, this value should be 0.</p>
</dd>
</dl>

## -returns
<p>If the operation is successful, the callback function must return STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE.</p>

<p>If the driver is unable to complete the remote retain transaction, it should return STATUS_ACCESS_DENIED so that the failure will bubble up to the application.</p>

<p>To define a <b>EVT_POS_CX_DEVICE_REMOTE_RETAIN</b> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <b>EVT_POS_CX_DEVICE_REMOTE_RETAIN</b> function that is named "MyEvtPosCxDeviceRemoteRetain", use the <b>EVT_POS_CX_DEVICE_REMOTE_RETAIN</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>EVT_POS_CX_DEVICE_REMOTE_RETAIN</b> function type is defined in the poscx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_POS_CX_DEVICE_REMOTE_RETAIN</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Product</p>
</th>
<td width="70%">
<p>Windows 10 or later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Poscx.h (include Poscx.h)</dt>
</dl>
</td>
</tr>
</table>