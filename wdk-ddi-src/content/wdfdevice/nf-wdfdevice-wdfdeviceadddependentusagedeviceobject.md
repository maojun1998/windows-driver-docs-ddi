---
UID: NF.wdfdevice.WdfDeviceAddDependentUsageDeviceObject
title: WdfDeviceAddDependentUsageDeviceObject
author: windows-driver-content
description: The WdfDeviceAddDependentUsageDeviceObject method indicates that a specified device depends on another device when the specified device is used to store special files.
old-location: wdf\wdfdeviceadddependentusagedeviceobject.htm
ms.assetid: 025046e2-ffa1-4210-b4aa-ab3d6b211066
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceAddDependentUsageDeviceObject
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: WdfDeviceAddDependentUsageDeviceObject
req.iface: 
req.product: Windows 10 or later.
---

# WdfDeviceAddDependentUsageDeviceObject function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfDeviceAddDependentUsageDeviceObject</b> method indicates that a specified device depends on another device when the specified device is used to store <a href="https://msdn.microsoft.com/3879570f-e083-4eaf-aa5b-9b78d8f826c1">special files</a>. </p>


## -syntax

````
NTSTATUS WdfDeviceAddDependentUsageDeviceObject(
  _In_ WDFDEVICE      Device,
  _In_ PDEVICE_OBJECT DependentDevice
);
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>

### -param <i>DependentDevice</i> [in]

<dd>
<p>A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that identifies a device that <i>Device</i> depends on.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, <b>WdfDeviceAddDependentUsageDeviceObject</b> method returns STATUS_SUCCESS. Additional return values include:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p><i>DependentDevice</i> is <b>NULL</b>.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>A memory allocation failed.</p>

<p> </p>

<p>The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>Your driver can call <b>WdfDeviceAddDependentUsageDeviceObject</b> to indicate that the device identified by <i>Device</i> depends on the device identified by <i>DependentDevice</i>, when <i>Device</i> supports special files. If your driver calls <b>WdfDeviceAddDependentUsageDeviceObject</b>, the framework calls the <a href="https://msdn.microsoft.com/b6b7dd80-fd91-4194-8288-4d703983a798">EvtDeviceUsageNotification</a> callback functions in <i>DependentDevice</i>'s drivers before it calls the <i>EvtDeviceUsageNotification</i> callback functions in <i>Device</i>'s drivers.</p>

<p>Your driver can call <b>WdfDeviceAddDependentUsageDeviceObject</b> multiple times to identify multiple devices that <i>Device</i> depends on to support special files.</p>

<p>After a driver has called <b>WdfDeviceAddDependentUsageDeviceObject</b>, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546829">WdfDeviceRemoveDependentUsageDeviceObject</a> to remove the device identified by <i>DependentDevice</i> from the list of devices that <i>Device</i> depends on.</p>

<p>For more information about special files, see <a href="wdf.supporting_special_files">Supporting Special Files</a>. </p>

<p>The following code example adds a device (<b>pDeviceObject</b>) to the list of devices that another device (<b>Device</b>) depends on.</p>

<p>Your driver can call <b>WdfDeviceAddDependentUsageDeviceObject</b> to indicate that the device identified by <i>Device</i> depends on the device identified by <i>DependentDevice</i>, when <i>Device</i> supports special files. If your driver calls <b>WdfDeviceAddDependentUsageDeviceObject</b>, the framework calls the <a href="https://msdn.microsoft.com/b6b7dd80-fd91-4194-8288-4d703983a798">EvtDeviceUsageNotification</a> callback functions in <i>DependentDevice</i>'s drivers before it calls the <i>EvtDeviceUsageNotification</i> callback functions in <i>Device</i>'s drivers.</p>

<p>Your driver can call <b>WdfDeviceAddDependentUsageDeviceObject</b> multiple times to identify multiple devices that <i>Device</i> depends on to support special files.</p>

<p>After a driver has called <b>WdfDeviceAddDependentUsageDeviceObject</b>, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546829">WdfDeviceRemoveDependentUsageDeviceObject</a> to remove the device identified by <i>DependentDevice</i> from the list of devices that <i>Device</i> depends on.</p>

<p>For more information about special files, see <a href="wdf.supporting_special_files">Supporting Special Files</a>. </p>

<p>The following code example adds a device (<b>pDeviceObject</b>) to the list of devices that another device (<b>Device</b>) depends on.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
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

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/b6b7dd80-fd91-4194-8288-4d703983a798">EvtDeviceUsageNotification</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546829">WdfDeviceRemoveDependentUsageDeviceObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAddDependentUsageDeviceObject method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>