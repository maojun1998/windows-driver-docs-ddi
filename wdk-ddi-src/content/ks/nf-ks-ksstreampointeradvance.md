---
UID: NF.ks.KsStreamPointerAdvance
title: KsStreamPointerAdvance
author: windows-driver-content
description: The KsStreamPointerAdvance function advances a stream pointer to the next data frame.
old-location: stream\ksstreampointeradvance.htm
ms.assetid: 98d0b8ce-5485-4584-b164-a1bc698b08ba
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: stream
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsStreamPointerAdvance
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
req.irql: <=DISPATCH_LEVEL
ms.keywords: KsStreamPointerAdvance
req.iface: 
---

# KsStreamPointerAdvance function



## -description
<p>The<b> KsStreamPointerAdvance </b>function advances a stream pointer to the next data frame.</p>


## -syntax

````
NTSTATUS KsStreamPointerAdvance(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````


## -parameters
<dl>

### -param <i>StreamPointer</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure representing the stream pointer to advance to reference the next available data frame.</p>
</dd>
</dl>

## -returns
<p><b>KsStreamPointerAdvance </b>returns STATUS_SUCCESS to indicate a successful advancement. It returns an error code otherwise. STATUS_DEVICE_NOT_READY is the most often returned error code and often indicates that locking the stream pointer after advancement failed. In other words, <i>StreamPointer</i> references the last frame in the queue.</p>

## -remarks
<p>If <i>StreamPointer</i> is locked at call-time, AVStream unlocks it before advancing it. Once advanced, the stream pointer is placed back into its original state (locked or unlocked) on the new frame.</p>

<p>An attempt to advance a stream pointer that is unlocked always succeeds and returns STATUS_SUCCESS. Since the stream pointer is not locked, there is no way to determine if the stream pointer references actual data. The minidriver must attempt a lock to determine if the newly advanced stream pointer references a data frame or not.</p>

<p>Also see <a href="NULL">Stream Pointers</a>.</p>

<p>If <i>StreamPointer</i> is locked at call-time, AVStream unlocks it before advancing it. Once advanced, the stream pointer is placed back into its original state (locked or unlocked) on the new frame.</p>

<p>An attempt to advance a stream pointer that is unlocked always succeeds and returns STATUS_SUCCESS. Since the stream pointer is not locked, there is no way to determine if the stream pointer references actual data. The minidriver must attempt a lock to determine if the newly advanced stream pointer references a data frame or not.</p>

<p>Also see <a href="NULL">Stream Pointers</a>.</p>

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
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
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
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567137">KsStreamPointerUnlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567126">KsStreamPointerAdvanceOffsets</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567127">KsStreamPointerAdvanceOffsetsAndUnlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerAdvance function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>