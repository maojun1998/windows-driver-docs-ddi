---
UID: NF.wdm.IoWMIQuerySingleInstance
title: IoWMIQuerySingleInstance
author: windows-driver-content
description: The IoWMIQuerySingleInstance routine returns the specified instance of a WMI data block.
old-location: kernel\iowmiquerysingleinstance.htm
ms.assetid: 742535da-4726-4320-88ec-f6752ad02fb3
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoWMIQuerySingleInstance
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
ms.keywords: IoWMIQuerySingleInstance
req.iface: 
req.product: Windows 10 or later.
---

# IoWMIQuerySingleInstance function



## -description
<p>The <b>IoWMIQuerySingleInstance</b> routine returns the specified instance of a WMI data block.</p>


## -syntax

````
NTSTATUS IoWMIQuerySingleInstance(
  _In_      PVOID           DataBlockObject,
  _In_      PUNICODE_STRING InstanceName,
  _Inout_   ULONG           *InOutBufferSize,
  _Out_opt_ PVOID           OutBuffer
);
````


## -parameters
<dl>

### -param <i>DataBlockObject</i> [in]

<dd>
<p>Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550453">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_QUERY access right.</p>
</dd>

### -param <i>InstanceName</i> [in]

<dd>
<p>Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.</p>
</dd>

### -param <i>InOutBufferSize</i> [in, out]

<dd>
<p>Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with status code of STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.</p>
</dd>

### -param <i>OutBuffer</i> [out, optional]

<dd>
<p>Pointer to the buffer where the routine returns the WMI data. The routine returns a variable-sized <a href="https://msdn.microsoft.com/library/windows/hardware/ff566377">WNODE_SINGLE_INSTANCE</a> structure. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool.</p>
</dd>
</dl>

## -returns
<p>The routine returns an NTSTATUS code. Possible return values include:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation succeeded. The routine returns the WMI data in the buffer pointed to by the <i>OutBuffer</i> parameter. The routine also returns the size, in bytes, of the returned data in the memory location pointed to by the <i>InOutBufferSize</i> parameter.</p><dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl><p>No drivers implement the specified WMI class.</p><dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl><p>No driver implements an instance of the WMI class with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter.</p>

<p> </p>

## -remarks
<p><b>IoWMIQuerySingleInstance</b> determines which drivers might support the specified WMI class with the specified instance name, and issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property returns the appropriate data.</p>

<p>To query for multiple WMI classes and instance names, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550477">IoWMIQuerySingleInstanceMultiple</a> routine. Drivers can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550493">IoWMISetSingleInstance</a> routine to update the class instance. </p>

<p><b>IoWMIQuerySingleInstance</b> determines which drivers might support the specified WMI class with the specified instance name, and issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property returns the appropriate data.</p>

<p>To query for multiple WMI classes and instance names, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550477">IoWMIQuerySingleInstanceMultiple</a> routine. Drivers can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550493">IoWMISetSingleInstance</a> routine to update the class instance. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows XP and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550453">IoWMIOpenBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550477">IoWMIQuerySingleInstanceMultiple</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550493">IoWMISetSingleInstance</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIQuerySingleInstance routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>