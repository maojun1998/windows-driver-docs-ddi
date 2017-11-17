---
UID: NS.ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
title: tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
author: windows-driver-content
description: This structure contains the header information for ROI ISP controls.
old-location: stream\kscamera_extendedprop_roi_ispcontrolheader.htm
ms.assetid: F57B0E44-A6A1-4C43-83EE-8DF4A605C0D0
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
req.alt-loc: Ksmedia.h
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
ms.keywords: tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
req.iface: 
---

# tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure



## -description
<p>This structure contains the header information for ROI ISP controls.</p>


## -syntax

````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER {
  ULONG     Size;
  ULONG     ControlCount;
  ULONGLONG Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The sum of this structure size, all <a href="https://msdn.microsoft.com/library/windows/hardware/dn925171">KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL</a> structures, and all KSCAMERA_EXTENDEDPROP_ROI_RECTINFO structures that follow</p>
</dd>

### -field <b>ControlCount</b>

<dd>
<p>The number of ISP controls. If this value is 0, the ROI control will remove all ROIs previously configured. This effectively clears up all ROIs configured and resets the driver to the default ROI.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for future use.</p>
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
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>