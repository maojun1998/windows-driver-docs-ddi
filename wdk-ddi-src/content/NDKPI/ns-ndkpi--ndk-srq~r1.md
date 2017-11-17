---
UID: NS.ndkpi._NDK_SRQ~r1
title: NDK_SRQ
author: windows-driver-content
description: The NDK_SRQ structure specifies the attributes of an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq.htm
ms.assetid: BDD2E8A6-D233-4581-AC1D-B6E33919898E
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
req.alt-api: NDK_SRQ
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
ms.keywords: NDK_SRQ, NDK_SRQ
req.iface: 
---

# NDK_SRQ structure



## -description
<p>The <b>NDK_SRQ</b> structure specifies the attributes of an NDK shared receive queue (SRQ) object.</p>


## -syntax

````
typedef struct _NDK_SRQ {
  NDK_OBJECT_HEADER      Header;
  CONST NDK_SRQ_DISPATCH *Dispatch;
} NDK_SRQ, *PNDK_SRQ;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure for the NDK_SRQ structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeSrq</b>.</p>
</dd>

### -field <b>Dispatch</b>

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439940">NDK_SRQ_DISPATCH</a> structure that defines dispatch functions for the NDK SRQ object.</p>
</dd>
</dl>

## -remarks
<p>An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439940">NDK_SRQ_DISPATCH</a> table before returning the  created SRQ object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439940">NDK_SRQ_DISPATCH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439880">NDK_FN_CREATE_QP_WITH_SRQ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439883">NDK_FN_CREATE_SRQ</a>
</dt>
<dt>
<a href="NULL">NDKPI Object Lifetime Requirements</a>
</dt>
<dt>
<a href="NULL">NDKPI Work Request Posting Requirements</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_SRQ structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>