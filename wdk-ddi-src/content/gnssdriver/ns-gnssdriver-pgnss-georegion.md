---
UID: NS.gnssdriver.PGNSS_GEOREGION
title: PGNSS_GEOREGION
author: windows-driver-content
description: This structure defines the geographical shape of a geofence.
old-location: sensors\gnss_georegion.htm
ms.assetid: 70FC3BCE-3869-4263-8870-BB97438CB5F1
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
req.alt-api: GNSS_GEOREGION
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
ms.keywords: PGNSS_GEOREGION, GNSS_GEOREGION, *PGNSS_GEOREGION
req.iface: 
---

# PGNSS_GEOREGION structure



## -description
<p>This structure defines the geographical shape of  a geofence.</p>


## -syntax

````
typedef struct {
  ULONG              Size;
  ULONG              Version;
  GNSS_GEOREGIONTYPE GeoRegionType;
  union {
    GNSS_GEOREGION_CIRCLE Circle;
    BYTE                  Unused[512];
  };
} GNSS_GEOREGION, *PGNSS_GEOREGION;
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

### -field <b>GeoRegionType</b>

<dd>
<p>
<a href="https://msdn.microsoft.com/736A1D63-A96E-4E29-ADFD-F441AC4757C6">GNSS_GEOREGIONTYP</a>E enumeration that defines the georegion type of a geofence.</p>
</dd>

### -field <b>Circle</b>

<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn925179">GNSS_GEOREGION_CIRCLE</a> structure that defines a circular geofence.</p>
</dd>

### -field <b>Unused[512]</b>

<dd>
<p>Padding buffer.</p>
</dd>
</dl>

## -remarks
<p>A geographical shape is used to define a geofence.  Windows 10 currently supports only circular geofences.</p>

<p></p>

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