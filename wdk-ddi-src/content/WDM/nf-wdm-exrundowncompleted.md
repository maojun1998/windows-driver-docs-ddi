---
UID: NF.wdm.ExRundownCompleted
title: ExRundownCompleted
author: windows-driver-content
description: The ExRundownCompleted routine updates the run-down status of a shared object to indicate that the run down of the object has completed.
old-location: kernel\exrundowncompleted.htm
ms.assetid: CF1650C2-4141-4AD7-A3FC-A800B2281A8A
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExRundownCompleted
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
ms.keywords: ExRundownCompleted
req.iface: 
req.product: Windows 10 or later.
---

# ExRundownCompleted function



## -description
<p>The <b>ExRundownCompleted</b> routine updates the run-down status of a shared object to indicate that the run down of the object has completed.</p>


## -syntax

````
VOID ExRundownCompleted(
  _Out_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters
<dl>

### -param <i>RunRef</i> [out]

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. The <b>ExRundownCompleted</b> call must be preceded by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569378">ExWaitForRundownProtectionRelease</a> routine that runs down the object.</p>

<p>After an <b>ExRundownCompleted</b> call, additional calls to <b>ExWaitForRundownProtectionRelease</b> to run down the associated object return immediately without waiting. However, calls to <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> to acquire run-down protection on the associated object fail (return <b>FALSE</b>).</p>

<p>After an <b>ExRundownCompleted</b> call, the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569374">ExReInitializeRundownProtection</a> routine to associate the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure with a new object and to initialize run-down protection on this object. After the <b>ExReInitializeRundownProtection</b> call, drivers can call <b>ExAcquireRundownProtection</b> to acquire run-down protection on the new object.</p>

<p>On entry, the status information in the <b>EX_RUNDOWN_REF</b> structure must indicate that the object that was associated with this structure was run down. Otherwise, <b>ExReInitializeRundownProtection</b> bug checks in checked builds.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.</p>

<p>This routine is called by the driver that owns an object that resides in shared memory and that is accessed by other drivers. The <b>ExRundownCompleted</b> call must be preceded by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569378">ExWaitForRundownProtectionRelease</a> routine that runs down the object.</p>

<p>After an <b>ExRundownCompleted</b> call, additional calls to <b>ExWaitForRundownProtectionRelease</b> to run down the associated object return immediately without waiting. However, calls to <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> to acquire run-down protection on the associated object fail (return <b>FALSE</b>).</p>

<p>After an <b>ExRundownCompleted</b> call, the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569374">ExReInitializeRundownProtection</a> routine to associate the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure with a new object and to initialize run-down protection on this object. After the <b>ExReInitializeRundownProtection</b> call, drivers can call <b>ExAcquireRundownProtection</b> to acquire run-down protection on the new object.</p>

<p>On entry, the status information in the <b>EX_RUNDOWN_REF</b> structure must indicate that the object that was associated with this structure was run down. Otherwise, <b>ExReInitializeRundownProtection</b> bug checks in checked builds.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.</p>

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
<p>Available starting with Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/jj569373">ExInitializeRundownProtection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExRundownCompleted routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>