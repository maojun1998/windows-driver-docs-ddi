---
UID: NS.iscsifnd._ReportDiscoveredTargets_OUT
title: ReportDiscoveredTargets_OUT
author: windows-driver-content
description: The ReportDiscoveredTargets_OUT structure holds the output data for the ReportDiscoveredTargets method.
old-location: storage\reportdiscoveredtargets_out.htm
ms.assetid: cecef33a-a192-41f4-8006-b5d8b8c73e8d
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReportDiscoveredTargets_OUT
req.alt-loc: iscsifnd.h
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
ms.keywords: ReportDiscoveredTargets_OUT, ReportDiscoveredTargets_OUT, *PReportDiscoveredTargets_OUT
req.iface: 
---

# ReportDiscoveredTargets_OUT structure



## -description
<p>The ReportDiscoveredTargets_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564046">ReportDiscoveredTargets</a> method.</p>


## -syntax

````
typedef struct _ReportDiscoveredTargets_OUT {
  ULONG                  Status;
  ULONG                  TargetCount;
  ISCSI_DiscoveredTarget Targets[1];
} ReportDiscoveredTargets_OUT, *PReportDiscoveredTargets_OUT;
````


## -struct-fields
<dl>

### -field <b>Status</b>

<dd>
<p>On output, the status of the <b>ReportDiscoveredTargets</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. </p>
</dd>

### -field <b>TargetCount</b>

<dd>
<p>On output, the number of targets that are discovered. </p>
</dd>

### -field <b>Targets</b>

<dd>
<p>On output, an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561501">ISCSI_DiscoveredTarget</a> structures, which provide information that is related to discovered targets. </p>
</dd>
</dl>

## -remarks
<p>You must implement this method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsifnd.h (include Iscsifnd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561501">ISCSI_DiscoveredTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564046">ReportDiscoveredTargets</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564054">ReportDiscoveredTargets2_OUT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20ReportDiscoveredTargets_OUT structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>