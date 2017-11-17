---
UID: NS.ndkpi._NDK_RESULT
title: NDK_RESULT
author: windows-driver-content
description: The NDK_RESULT structure returns the results for an NDK request operation.
old-location: netvista\ndk_result.htm
ms.assetid: B7898C81-E90D-4210-BEAE-1E629FCD7195
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_RESULT
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: NDK_RESULT, NDK_RESULT
req.iface: 
---

# NDK_RESULT structure



## -description
<p>The <b>NDK_RESULT</b> structure returns the results for an NDK request operation. </p>


## -syntax

````
typedef struct _NDK_RESULT {
  NTSTATUS Status;
  ULONG    BytesTransferred;
  PVOID    QPContext;
  PVOID    RequestContext;
} NDK_RESULT;
````


## -struct-fields
<dl>

### -field <b>Status</b>

<dd>
<p>The NDK request completion status.</p>
</dd>

### -field <b>BytesTransferred</b>

<dd>
<p>The number of bytes transferred. The value of this member  is valid only for <i>NdkReceive</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a>) request completions. The member is undefined for all other NDK request completions.</p>
</dd>

### -field <b>QPContext</b>

<dd>
<p>A context value for all requests that are posted over a queue pair (QP). The NDK consumer specified this  pointer when it called the <i>NdkCreateQp</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439878">NDK_FN_CREATE_QP</a>) function to create the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a> object.</p>
</dd>

### -field <b>RequestContext</b>

<dd>
<p>A request context value specified by the NDK consumer when  a request is posted.</p>
</dd>
</dl>

## -remarks
<p> The <i>NdkGetCqResults</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439891">NDK_FN_GET_CQ_RESULTS</a>)  function gets an array of <b>NDK_RESULT</b> structures that are filled with completion results that were removed from the CQ.

</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439878">NDK_FN_CREATE_QP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439891">NDK_FN_GET_CQ_RESULTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_RESULT structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>