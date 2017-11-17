---
UID: NF.ks.KsAllocateDeviceHeader
title: KsAllocateDeviceHeader
author: windows-driver-content
description: The KsAllocateDeviceHeader function allocates and initializes the required device extension header.
old-location: stream\ksallocatedeviceheader.htm
ms.assetid: 554f03bf-cacd-401b-aa34-fcfe1c31091e
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsAllocateDeviceHeader
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
ms.keywords: KsAllocateDeviceHeader
req.iface: 
---

# KsAllocateDeviceHeader function



## -description
<p>The <b>KsAllocateDeviceHeader</b> function allocates and initializes the required device extension header. </p>


## -syntax

````
NTSTATUS KsAllocateDeviceHeader(
  _Out_    KSDEVICE_HEADER       *Header,
  _In_     ULONG                 ItemsCount,
  _In_opt_ PKSOBJECT_CREATE_ITEM ItemsList
);
````


## -parameters
<dl>

### -param <i>Header</i> [out]

<dd>
<p>Points to the location in which to return a pointer to the initialized header.</p>
</dd>

### -param <i>ItemsCount</i> [in]

<dd>
<p>Specifies the number of subitems in the <i>ItemsList</i>. This should be zero if an <i>ItemsList</i> is not passed.</p>
</dd>

### -param <i>ItemsList</i> [in, optional]

<dd>
<p>Optional. Points to a KSOBJECT_CREATE_ITEM structure for each subitem. If there are no subitems, this value should be <b>NULL</b> and <i>ItemsCount</i> should be zero.</p>
</dd>
</dl>

## -returns
<p>The <b>KsAllocateDeviceHeader</b> function returns STATUS_SUCCESS if successful or STATUS_INSUFFICIENT_RESOURCES if unable to allocate the necessary resources.</p>

## -remarks
<p>The <b>KsAllocateDeviceHeader</b> function allocates memory for the KSDEVICE_HEADER structure for a device. When the header is no longer needed, the driver should call the <b>KsFreeDeviceHeader</b> function to free the memory allocated.</p>

<p>If subobjects exist for a given device, the driver must, before calling <b>KsAllocateDeviceHeader</b>, allocate a buffer of either paged or nonpaged memory of sufficient size to hold a KSOBJECT_CREATE_ITEM structure for each subobject. For example:</p>

<p>Drivers must not free the memory allocated for the subobject KSOBJECT_CREATE_ITEM list until after calling <b>KsFreeDeviceHeader</b>. Failure to do so can result in a bug check condition. </p>

<p>The <b>KsAllocateDeviceHeader</b> function allocates memory for the KSDEVICE_HEADER structure for a device. When the header is no longer needed, the driver should call the <b>KsFreeDeviceHeader</b> function to free the memory allocated.</p>

<p>If subobjects exist for a given device, the driver must, before calling <b>KsAllocateDeviceHeader</b>, allocate a buffer of either paged or nonpaged memory of sufficient size to hold a KSOBJECT_CREATE_ITEM structure for each subobject. For example:</p>

<p>Drivers must not free the memory allocated for the subobject KSOBJECT_CREATE_ITEM list until after calling <b>KsFreeDeviceHeader</b>. Failure to do so can result in a bug check condition. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562560">KsFreeDeviceHeader</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAllocateDeviceHeader function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>