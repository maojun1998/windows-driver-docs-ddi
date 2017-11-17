---
UID: NF.wdm.ExInterlockedAddLargeInteger
title: ExInterlockedAddLargeInteger
author: windows-driver-content
description: The ExInterlockedAddLargeInteger routine adds a large integer value to the specified variable as an atomic operation.
old-location: kernel\exinterlockedaddlargeinteger.htm
ms.assetid: ace8405b-74a7-4797-8d3d-3caf673dace2
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not available in Windows 98 or Windows Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExInterlockedAddLargeInteger
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
req.irql: Any level (see Remarks section)
ms.keywords: ExInterlockedAddLargeInteger
req.iface: 
req.product: Windows 10 or later.
---

# ExInterlockedAddLargeInteger function



## -description
<p>The <b>ExInterlockedAddLargeInteger</b> routine adds a large integer value to the specified variable as an atomic operation.</p>


## -syntax

````
LARGE_INTEGER ExInterlockedAddLargeInteger(
  _Inout_ PLARGE_INTEGER Addend,
  _In_    LARGE_INTEGER  Increment,
  _Inout_ PKSPIN_LOCK    Lock
);
````


## -parameters
<dl>

### -param <i>Addend</i> [in, out]

<dd>
<p>A pointer to the variable to be adjusted by the <i>Increment</i> value. </p>
</dd>

### -param <i>Increment</i> [in]

<dd>
<p>Specifies a value to be added to <i>Addend</i>. </p>
</dd>

### -param <i>Lock</i> [in, out]

<dd>
<p>A pointer to a spin lock to be used to synchronize access to <i>Addend</i>. </p>
</dd>
</dl>

## -returns
<p><b>ExInterlockedAddLargeInteger</b> returns the initial value of the <i>Addend </i>parameter.</p>

## -remarks
<p>Support routines that do interlocked operations are assumed to be incapable of causing a page fault. That is, neither their code nor any of the data they touch can cause a page fault without bringing down the system. They use spin locks to achieve atomicity on symmetric multiprocessor machines. The caller must provide resident storage for the <i>Lock</i>, which must be initialized with <b>KeInitializeSpinLock</b> before the initial call to an <b>ExInterlocked<i>Xxx</i></b>.</p>

<p>The <i>Lock</i> passed to <b>ExInterlockedAddLargeInteger</b> is used to assure that the add operation on <i>Addend</i> is atomic with respect to any other operations on the same value which synchronize with this same spin lock. </p>

<p><b>ExInterlockedAddLargeInteger</b> masks interrupts. Consequently, it can be used for synchronization between an ISR and other device driver code, provided that the same <i>Lock</i> is never reused in a call to a routine that runs at IRQL = DISPATCH_LEVEL.</p>

<p>Note that calls to <b>Interlocked<i>Xxx</i></b> are guaranteed to be atomic with respect to other <b>Interlocked<i>Xxx</i></b> calls without caller-supplied spin locks.</p>

<p>Callers of <b>ExInterlockedAddLargeInteger</b> run at any IRQL. The storage for the <i>Addend</i> parameter must be resident at all IRQLs.</p>

<p>Support routines that do interlocked operations are assumed to be incapable of causing a page fault. That is, neither their code nor any of the data they touch can cause a page fault without bringing down the system. They use spin locks to achieve atomicity on symmetric multiprocessor machines. The caller must provide resident storage for the <i>Lock</i>, which must be initialized with <b>KeInitializeSpinLock</b> before the initial call to an <b>ExInterlocked<i>Xxx</i></b>.</p>

<p>The <i>Lock</i> passed to <b>ExInterlockedAddLargeInteger</b> is used to assure that the add operation on <i>Addend</i> is atomic with respect to any other operations on the same value which synchronize with this same spin lock. </p>

<p><b>ExInterlockedAddLargeInteger</b> masks interrupts. Consequently, it can be used for synchronization between an ISR and other device driver code, provided that the same <i>Lock</i> is never reused in a call to a routine that runs at IRQL = DISPATCH_LEVEL.</p>

<p>Note that calls to <b>Interlocked<i>Xxx</i></b> are guaranteed to be atomic with respect to other <b>Interlocked<i>Xxx</i></b> calls without caller-supplied spin locks.</p>

<p>Callers of <b>ExInterlockedAddLargeInteger</b> run at any IRQL. The storage for the <i>Addend</i> parameter must be resident at all IRQLs.</p>

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
<p>Available in Windows 2000 and later versions of Windows. Not available in Windows 98 or Windows Me.</p>
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
<p>Any level (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545343">ExInterlockedAddUlong</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547910">InterlockedIncrement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547871">InterlockedDecrement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedAddLargeInteger routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>