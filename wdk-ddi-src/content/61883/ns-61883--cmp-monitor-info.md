---
UID: NS.61883._CMP_MONITOR_INFO
title: CMP_MONITOR_INFO
author: windows-driver-content
description: The CMP_MONITOR_INFO structure is used in conjunction with the Av61883_MonitorPlugs request to allow a driver to monitor access to local oPCR and iPCR plugs.
old-location: ieee\cmp_monitor_info.htm
ms.assetid: 258bcd6f-0536-48d3-a06a-10277f8bef87
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: IEEE
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CMP_MONITOR_INFO
req.alt-loc: 61883.h
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
ms.keywords: CMP_MONITOR_INFO, CMP_MONITOR_INFO, *PCMP_MONITOR_INFO
---

# CMP_MONITOR_INFO structure



## -description
<p>The CMP_MONITOR_INFO structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a> request to allow a driver to monitor access to local oPCR and iPCR plugs.</p>


## -syntax

````
typedef struct _CMP_MONITOR_INFO {
  ULONG  State;
  ULONG  PlugNum;
  ULONG  PlugType;
  AV_PCR Pcr;
  PVOID  Context;
} CMP_MONITOR_INFO, *PCMP_MONITOR_INFO;
````


## -struct-fields
<dl>

### -field <b>State</b>

<dd>
<p>The current state of the plug.</p>
</dd>

### -field <b>PlugNum</b>

<dd>
<p>The number of the plug that was accessed.</p>
</dd>

### -field <b>PlugType</b>

<dd>
<p>The type of plug, either CMP_PlugOut or CMP_PlugIn.</p>
</dd>

### -field <b>Pcr</b>

<dd>
<p>The current contents of the plug.</p>
</dd>

### -field <b>Context</b>

<dd>
<p>Points to a caller-defined context that was registered with <a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a>.</p>
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
<dt>61883.h (include 61883.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_MONITOR_INFO structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>