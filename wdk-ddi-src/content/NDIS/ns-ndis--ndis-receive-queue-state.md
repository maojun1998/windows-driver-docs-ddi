---
UID: NS.ndis._NDIS_RECEIVE_QUEUE_STATE
title: NDIS_RECEIVE_QUEUE_STATE
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_STATE structure contains information about the operational state of a receive queue.
old-location: netvista\ndis_receive_queue_state.htm
ms.assetid: e997fce6-ee3a-433f-b9b7-3e2932093a1a
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RECEIVE_QUEUE_STATE
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
ms.keywords: NDIS_RECEIVE_QUEUE_STATE, NDIS_RECEIVE_QUEUE_STATE, *PNDIS_RECEIVE_QUEUE_STATE
req.iface: 
---

# NDIS_RECEIVE_QUEUE_STATE structure



## -description
<p>The <b>NDIS_RECEIVE_QUEUE_STATE</b> structure contains information about the operational state of a receive
  queue.</p>


## -syntax

````
typedef struct _NDIS_RECEIVE_QUEUE_STATE {
  NDIS_OBJECT_HEADER                   Header;
  ULONG                                Flags;
  NDIS_RECEIVE_QUEUE_ID                QueueId;
  NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE QueueState;
} NDIS_RECEIVE_QUEUE_STATE, *PNDIS_RECEIVE_QUEUE_STATE;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_STATE</b>  structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_STATE_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_RECEIVE_QUEUE_STATE_REVISION_1</b>.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.</p>
</dd>

### -field <b>QueueId</b>

<dd>
<p>An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a queue identifier. The queue identifier is an
     integer value between zero and the number of queues that the network adapter supports. A value of <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b> specifies
     the default receive queue.</p>
</dd>

### -field <b>QueueState</b>

<dd>
<p>An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567208">NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a> enumeration value that specifies the operational state of the
     receive queue.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDIS_RECEIVE_QUEUE_STATE</b> structure is used in the 
    <a href="netvista.ndis_status_receive_queue_state">
    NDIS_STATUS_RECEIVE_QUEUE_STATE</a> status indication.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.20 and later.</p>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a8ae7b19-9dc8-4ccc-b71e-62ec0be1fa99">
   NDIS_RECEIVE_QUEUE_OPERATIONAL_STATE</a>
</dt>
<dt>
<a href="netvista.ndis_status_receive_queue_state">
   NDIS_STATUS_RECEIVE_QUEUE_STATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_STATE structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>