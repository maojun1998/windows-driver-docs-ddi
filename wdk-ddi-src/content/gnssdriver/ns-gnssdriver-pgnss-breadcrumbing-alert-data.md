---
UID: NS.gnssdriver.PGNSS_BREADCRUMBING_ALERT_DATA
title: PGNSS_BREADCRUMBING_ALERT_DATA
author: windows-driver-content
description: This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed.
old-location: sensors\gnss_breadcrumbing_alert_data.htm
ms.assetid: 5B8C1264-336C-438F-89AC-82B6FCBAE931
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: sensors
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_BREADCRUMBING_ALERT_DATA
req.alt-loc: gnssdriver.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: PGNSS_BREADCRUMBING_ALERT_DATA, GNSS_BREADCRUMBING_ALERT_DATA, *PGNSS_BREADCRUMBING_ALERT_DATA
req.iface: 
---

# PGNSS_BREADCRUMBING_ALERT_DATA structure



## -description
<p>This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed.</p>


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  BYTE  Unused[512];
} GNSS_BREADCRUMBING_ALERT_DATA, *PGNSS_BREADCRUMBING_ALERT_DATA;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>Structure size.</p>
</dd>

### -field <b>Version</b>

<dd>
<p>Version number.</p>
</dd>

### -field <b>Unused[512]</b>

<dd>
<p>Padding buffer.</p>
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
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>