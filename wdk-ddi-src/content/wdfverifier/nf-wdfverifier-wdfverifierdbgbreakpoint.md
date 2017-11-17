---
UID: NF.wdfverifier.WdfVerifierDbgBreakPoint
title: WdfVerifierDbgBreakPoint
author: windows-driver-content
description: The WdfVerifierDbgBreakPoint function breaks into a kernel debugger, if a debugger is running.
old-location: wdf\wdfverifierdbgbreakpoint.htm
ms.assetid: 55b8a6de-f20b-4d2d-8235-4837bc4a0d7d
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfverifier.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfVerifierDbgBreakPoint
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
ms.keywords: WdfVerifierDbgBreakPoint
req.iface: 
req.product: Windows 10 or later.
---

# WdfVerifierDbgBreakPoint function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger, if a debugger is running.</p>


## -syntax

````
VOID WdfVerifierDbgBreakPoint(void);
````


## -parameters


## -returns
<p>None</p>

<p>None</p>

<p>None</p>

## -remarks
<p>The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:</p>

<p>For more information about registry entries that you can use to debug your driver, see <a href="wdf.registry_values_for_debugging_kmdf_drivers">Registry Entries for Debugging Framework-Based Drivers</a>.</p>

<p>For more information about debugging your driver, see <a href="wdf.debugging_a_kmdf_driver">Debugging a KMDF Driver</a>.</p>

<p>The following code example shows how a driver might handle a failure to obtain an I/O request's output buffer.</p>

<p>The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:</p>

<p>For more information about registry entries that you can use to debug your driver, see <a href="wdf.registry_values_for_debugging_kmdf_drivers">Registry Entries for Debugging Framework-Based Drivers</a>.</p>

<p>For more information about debugging your driver, see <a href="wdf.debugging_a_kmdf_driver">Debugging a KMDF Driver</a>.</p>

<p>The following code example shows how a driver might handle a failure to obtain an I/O request's output buffer.</p>

<p>The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:</p>

<p>For more information about registry entries that you can use to debug your driver, see <a href="wdf.registry_values_for_debugging_kmdf_drivers">Registry Entries for Debugging Framework-Based Drivers</a>.</p>

<p>For more information about debugging your driver, see <a href="wdf.debugging_a_kmdf_driver">Debugging a KMDF Driver</a>.</p>

<p>The following code example shows how a driver might handle a failure to obtain an I/O request's output buffer.</p>

<p>The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:</p>

<p>For more information about registry entries that you can use to debug your driver, see <a href="wdf.registry_values_for_debugging_kmdf_drivers">Registry Entries for Debugging Framework-Based Drivers</a>.</p>

<p>For more information about debugging your driver, see <a href="wdf.debugging_a_kmdf_driver">Debugging a KMDF Driver</a>.</p>

<p>The following code example shows how a driver might handle a failure to obtain an I/O request's output buffer.</p>

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
<dt>Wdfverifier.h (include Wdf.h)</dt>
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
<p>Any level</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551166">WdfVerifierKeBugCheck</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfVerifierDbgBreakPoint function%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>