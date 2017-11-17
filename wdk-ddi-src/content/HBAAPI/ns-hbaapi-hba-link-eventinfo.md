---
UID: NS.hbaapi.HBA_Link_EventInfo
title: HBA_Link_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API.
old-location: storage\hba_link_eventinfo.htm
ms.assetid: be682bc7-61cb-40bd-920d-bc2224d6e426
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_LINK_EVENTINFO
req.alt-loc: hbaapi.h
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
ms.keywords: HBA_Link_EventInfo, HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO
req.iface: 
---

# HBA_Link_EventInfo structure



## -description
<p>The HBA_Link_EventInfo structure contains information about a WMI link event associated with the fibre channel HBA API. </p>


## -syntax

````
typedef struct HBA_Link_EventInfo {
  HBA_UINT32 PortFcId;
  HBA_UINT32 Reserved[3];
} HBA_LINK_EVENTINFO, *PHBA_LINK_EVENTINFO;
````


## -struct-fields
<dl>

### -field <b>PortFcId</b>

<dd>
<p>Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556048">HBA_EventInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557125">HBA_Pty_EventInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557188">HBA_RSCN_EventInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20HBA_Link_EventInfo structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>