---
UID: NF.wdfresource.WdfCmResourceListGetCount
title: WdfCmResourceListGetCount
author: windows-driver-content
description: The WdfCmResourceListGetCount method returns the number of resource descriptors that are contained in a specified resource list.
old-location: wdf\wdfcmresourcelistgetcount.htm
ms.assetid: f1a38276-4964-422d-9b3c-8450b1028f27
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfCmResourceListGetCount
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: WdfCmResourceListGetCount
req.iface: 
req.product: Windows 10 or later.
---

# WdfCmResourceListGetCount function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfCmResourceListGetCount</b> method returns the number of resource descriptors that are contained in a specified resource list.</p>


## -syntax

````
ULONG WdfCmResourceListGetCount(
  _In_ WDFCMRESLIST List
);
````


## -parameters
<dl>

### -param <i>List</i> [in]

<dd>
<p>A handle to a framework resource-list object that represents a list of hardware resources for a device.</p>
</dd>
</dl>

## -returns
<p><b>WdfCmResourceListGetCount</b> returns the number of resource descriptors that are contained in the resource list that the <i>List</i> parameter specifies.</p>

<p>A system bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>For more information about resource lists, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.</p>

<p>The following code example shows how an <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function might locate the memory, port, and interrupt resources in the list of <a href="wdf.raw_and_translated_resources">translated hardware resources</a> that the Plug and Play (PnP) manager has assigned to a device.</p>

<p>For more information about resource lists, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.</p>

<p>The following code example shows how an <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function might locate the memory, port, and interrupt resources in the list of <a href="wdf.raw_and_translated_resources">translated hardware resources</a> that the Plug and Play (PnP) manager has assigned to a device.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfresource.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>