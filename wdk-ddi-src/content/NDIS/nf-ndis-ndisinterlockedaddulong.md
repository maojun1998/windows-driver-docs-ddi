---
UID: NF.ndis.NdisInterlockedAddUlong
title: NdisInterlockedAddUlong
author: windows-driver-content
description: The NdisInterlockedAddUlong function adds an unsigned long value to a given unsigned integer as an atomic operation, using a caller-supplied spin lock to synchronize access to the integer variable.
old-location: netvista\ndisinterlockedaddulong.htm
ms.assetid: d2e31f3c-7152-4df9-8206-a15dee9b641f
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   NdisInterlockedAddUlong (NDIS
   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   NdisInterlockedAddUlong (NDIS
   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisInterlockedAddUlong
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
ms.keywords: NdisInterlockedAddUlong
req.iface: 
---

# NdisInterlockedAddUlong function



## -description
<p>The 
  <b>NdisInterlockedAddUlong</b> function adds an unsigned long value to a given unsigned integer as an atomic
  operation, using a caller-supplied spin lock to synchronize access to the integer variable.</p>


## -syntax

````
VOID NdisInterlockedAddUlong(
  _In_ PULONG          Addend,
  _In_ ULONG           Increment,
  _In_ PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters
<dl>

### -param <i>Addend</i> [in]

<dd>
<p>A pointer to the variable for which the value is to be adjusted by the given 
     <i>Increment</i> .</p>
</dd>

### -param <i>Increment</i> [in]

<dd>
<p>The value to be added to that at 
     <i>Addend</i> .</p>
</dd>

### -param <i>SpinLock</i> [in]

<dd>
<p>A pointer to a caller-initialized spin lock.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The caller of 
    <b>NdisInterlockedAddUlong</b> must provide resident storage for the spin lock, which must be initialized
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function before
    the initial call to 
    <b>NdisInterlockedAddUlong</b>.</p>

<p>The 
    <i>SpinLock</i> value that is passed to the 
    <b>NdisInterlockedAddUlong</b> function
    is used to assure that the addition to the variable at the 
    <i>Addend</i> parameter is atomic with respect to any other operations on the same variable that
    synchronize with the same spin lock.</p>

<p><b>NdisInterlockedAddUlong</b> raises the IRQL to DISPATCH_LEVEL when it acquires the given spin lock and
    restores the original IRQL before it returns control. Consequently, any driver function that calls 
    <b>NdisInterlockedAddUlong</b> cannot be pageable code.</p>

<p>The caller of 
    <b>NdisInterlockedAddUlong</b> must provide resident storage for the spin lock, which must be initialized
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a> function before
    the initial call to 
    <b>NdisInterlockedAddUlong</b>.</p>

<p>The 
    <i>SpinLock</i> value that is passed to the 
    <b>NdisInterlockedAddUlong</b> function
    is used to assure that the addition to the variable at the 
    <i>Addend</i> parameter is atomic with respect to any other operations on the same variable that
    synchronize with the same spin lock.</p>

<p><b>NdisInterlockedAddUlong</b> raises the IRQL to DISPATCH_LEVEL when it acquires the given spin lock and
    restores the original IRQL before it returns control. Consequently, any driver function that calls 
    <b>NdisInterlockedAddUlong</b> cannot be pageable code.</p>

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
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/e863c5a8-2559-4315-9f94-a51a61a79755">NdisInterlockedAddUlong (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisInterlockedAddUlong (NDIS
   5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560699">NdisAcquireSpinLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561617">NdisAllocateSpinLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564532">NdisRetrieveUlong</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564573">NdisStoreUlong</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedAddUlong function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>