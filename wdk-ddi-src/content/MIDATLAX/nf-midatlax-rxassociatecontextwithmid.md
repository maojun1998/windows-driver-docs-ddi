---
UID: NF.midatlax.RxAssociateContextWithMid
title: RxAssociateContextWithMid
author: windows-driver-content
description: RxAssociateContextWithMid associates the supplied opaque context with an available multiplex ID (MID) from a MID_ATLAS.
old-location: ifsk\rxassociatecontextwithmid.htm
ms.assetid: b2ced4fb-5104-4bf3-8c6c-bf129e3dff97
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: midatlax.h
req.include-header: Midatlax.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxAssociateContextWithMid
req.alt-loc: midatlax.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
ms.keywords: RxAssociateContextWithMid
req.iface: 
---

# RxAssociateContextWithMid function



## -description
<p><b>RxAssociateContextWithMid</b> associates the supplied opaque context with an available multiplex ID (MID) from a MID_ATLAS. </p>


## -syntax

````
NTSTATUS RxAssociateContextWithMid(
   PRX_MID_ATLAS pMidAtlas,
   PVOID         pContext,
   PUSHORT       pNewMid
);
````


## -parameters
<dl>

### -param <i>pMidAtlas</i> 

<dd>
<p>A pointer to the MID_ATLAS data structure.</p>
</dd>

### -param <i>pContext</i> 

<dd>
<p>A pointer to the context.</p>
</dd>

### -param <i>pNewMid</i> 

<dd>
<p>A pointer to the multiplex ID to be associated with the context.</p>
</dd>
</dl>

## -returns
<p><b>RxAssociateContextWithMid</b> returns STATUS_SUCCESS on success or one of the following error values: </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>This error is returned when it was not possible to allocate sufficient memory for the new MID_MAP data structure.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><p>This error is returned for several cases including when the number of MIDs already in use is greater than the maximum number of MIDs set when the MID_ATLAS structure was created.</p>

<p> </p>

## -remarks
<p>RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. <b>RxAssociateContextWithMid</b> allocates non-paged pool memory when creating a new MID_MAP data structure.</p>

<p>The <i>pContext</i> parameter can be any opaque context but it is commonly an RX_CONTEXT. </p>

<p>RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. <b>RxAssociateContextWithMid</b> allocates non-paged pool memory when creating a new MID_MAP data structure.</p>

<p>The <i>pContext</i> parameter can be any opaque context but it is commonly an RX_CONTEXT. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Midatlax.h (include Midatlax.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554352">RxCreateMidAtlas</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554395">RxDestroyMidAtlas</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554545">RxMapMidToContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554541">RxMapAndDissociateMidFromContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554686">RxReassociateMid</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxAssociateContextWithMid function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>