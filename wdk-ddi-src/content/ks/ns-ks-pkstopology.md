---
UID: NS.ks.PKSTOPOLOGY
title: PKSTOPOLOGY
author: windows-driver-content
description: The KSTOPOLOGY structure describes the topology of pins and nodes.
old-location: stream\kstopology.htm
ms.assetid: 8dbd37ed-5d71-43bd-a3ca-caa5b0d08075
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSTOPOLOGY
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: PKSTOPOLOGY, KSTOPOLOGY, *PKSTOPOLOGY
req.iface: 
---

# PKSTOPOLOGY structure



## -description
<p>The KSTOPOLOGY structure describes the topology of pins and nodes.</p>


## -syntax

````
typedef struct {
  ULONG                       CategoriesCount;
  const GUID                  *Categories;
  ULONG                       TopologyNodesCount;
  const GUID                  *TopologyNodes;
  ULONG                       TopologyConnectionsCount;
  const KSTOPOLOGY_CONNECTION *TopologyConnections;
  const GUID                  *TopologyNodesNames;
  ULONG                       Reserved;
} KSTOPOLOGY, *PKSTOPOLOGY;
````


## -struct-fields
<dl>

### -field <b>CategoriesCount</b>

<dd>
<p>Specifies the number of functional categories that the driver supports.</p>
</dd>

### -field <b>Categories</b>

<dd>
<p>Points to the beginning of the array of functional categories that the driver supports.</p>
</dd>

### -field <b>TopologyNodesCount</b>

<dd>
<p>Specifies the number of nodes that the driver supports.</p>
</dd>

### -field <b>TopologyNodes</b>

<dd>
<p>Points to the beginning of the array of GUIDs that describe the type of each node. For a list of video kernel streaming related nodes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560886">Kernel Streaming Topology Nodes</a>. For a list of audio kernel streaming related nodes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536219">Audio Topology Nodes</a>.</p>
</dd>

### -field <b>TopologyConnectionsCount</b>

<dd>
<p>Specifies the number of entries in the array pointed to by <b>TopologyConnections</b>. The node numbers of each entry must correspond to the array offset of the node within <b>TopologyNodes</b>. When this structure is a part of a streaming minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559690">HW_STREAM_HEADER</a>, the pin numbers must correspond to the offsets within the array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a> structures in the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559686">HW_STREAM_DESCRIPTOR</a> structure.</p>
</dd>

### -field <b>TopologyConnections</b>

<dd>
<p>Points to the beginning of the array of topology connections for this structure.</p>
</dd>

### -field <b>TopologyNodesNames</b>

<dd>
<p>Specifies the GUID of the localized Unicode string name for the node, stored in the registry.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for system use. Drivers should set this to zero.</p>
</dd>
</dl>

## -remarks
<p>A stream class minidriver creates and passes this structure as part of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff559690">HW_STREAM_HEADER</a> structure. The class driver uses this structure to process topology property requests. The property data that the class driver returns is determined from the KSTOPOLOGY structure as follows:</p>

<p></p><dl>
<dt><a id="KSPROPERTY_TOPOLOGY_CATEGORIES"></a><a id="ksproperty_topology_categories"></a>KSPROPERTY_TOPOLOGY_CATEGORIES</dt>
<dd>
<p>Returns the array that begins at the <b>Categories</b> member of KSTOPOLOGY.</p>
</dd>
<dt><a id="KSPROPERTY_TOPOLOGY_CONNECTIONS"></a><a id="ksproperty_topology_connections"></a>KSPROPERTY_TOPOLOGY_CONNECTIONS</dt>
<dd>
<p>Returns the array that begins at the <b>TopologyConnections</b> member of KSTOPOLOGY.</p>
</dd>
<dt><a id="KSPROPERTY_TOPOLOGY_NAME"></a><a id="ksproperty_topology_name"></a>KSPROPERTY_TOPOLOGY_NAME</dt>
<dd></dd>
<dt><a id="KSPROPERTY_TOPOLOGY_NODES"></a><a id="ksproperty_topology_nodes"></a>KSPROPERTY_TOPOLOGY_NODES</dt>
<dd>
<p>Returns the array that begins at the <b>Nodes</b> member of KSTOPOLOGY.</p>
</dd>
</dl><p>Returns the array that begins at the <b>Categories</b> member of KSTOPOLOGY.</p>

<p>Returns the array that begins at the <b>TopologyConnections</b> member of KSTOPOLOGY.</p>

<p>Returns the array that begins at the <b>Nodes</b> member of KSTOPOLOGY.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559690">HW_STREAM_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559686">HW_STREAM_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567148">KSTOPOLOGY_CONNECTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSTOPOLOGY structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>