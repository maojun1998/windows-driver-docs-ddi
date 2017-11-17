---
UID: NS.sdpnode._SDP_NODE_HEADER
title: SDP_NODE_HEADER
author: windows-driver-content
description: The SDP_NODE_HEADER structure holds information about an element in a tree-based representation of an SDP record.
old-location: bltooth\sdp_node_header.htm
ms.assetid: 2c756db7-b7a9-493a-8fb1-8bbc741f8c63
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: bltooth
req.header: sdpnode.h
req.include-header: Sdpnode.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SDP_NODE_HEADER
req.alt-loc: sdpnode.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
ms.keywords: SDP_NODE_HEADER, SDP_NODE_HEADER, *PSDP_NODE_HEADER
req.iface: 
req.product: Windows 10 or later.
---

# SDP_NODE_HEADER structure



## -description
<p>The SDP_NODE_HEADER structure holds information about an element in a tree-based representation of an
  SDP record.</p>


## -syntax

````
typedef struct _SDP_NODE_HEADER {
  LIST_ENTRY Link;
  USHORT     Type;
  USHORT     SpecificType;
} SDP_NODE_HEADER, *PSDP_NODE_HEADER;
````


## -struct-fields
<dl>

### -field <b>Link</b>

<dd>
<p>A linked-list structure that is used to link peer SDP record nodes when this structure is part of
     an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structure. This member is used to link the
     first child of the node when the header is 
     <b>u.sequence</b> or 
     <b>u.alternative</b> part of the individual SDP_NODE structure.</p>
</dd>

### -field <b>Type</b>

<dd>
<p>The data type of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a> union held in the 
     <b>u</b> member of the SDP_NODE structure.</p>
</dd>

### -field <b>SpecificType</b>

<dd>
<p>Extra information about the data type associated with the 
     <b>SDP_NODE_DATA</b> union that is associated with the SDP record element.</p>
</dd>
</dl>

## -remarks
<p>Each SDP_NODE structure in the tree representation of an SDP record contains a SDP_NODE_HEADER
    structure and an 
    <b>SDP_NODE_DATA</b> union.</p>

<p>The header specifies the type of data. Driver developers can access links to peer SDP_NODE structures
    by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure of the header. By evaluating 
    <code>Node.hdr.Link.Flink</code>and 
    <code>Node.hdr.Link.Blink</code>, drivers can obtain the addresses of peer
    nodes in the tree. Keep in mind that 
    <b>LIST_ENTRY</b> pointers contain the address of other LIST_ENTRY structures, and that the profile driver
    must use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a> memory manager macro to
    extract the address of the containing node record.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Supported in Windows Vista, and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Sdpnode.h (include Sdpnode.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536849">SDP_NODE_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542043">CONTAINING_RECORD</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SDP_NODE_HEADER structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>