---
UID: NS.windot11._DOT11_WPS_DEVICE_NAME
title: DOT11_WPS_DEVICE_NAME
author: windows-driver-content
description: The DOT11_WPS_DEVICE_NAME structure contains a friendly name of the P2P device.
old-location: netvista\dot11_wps_device_name.htm
ms.assetid: 6C2B8E87-A88F-4244-81B2-0241E2DAE756
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WPS_DEVICE_NAME
req.alt-loc: Windot11.h
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
ms.keywords: DOT11_WPS_DEVICE_NAME, DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.iface: 
req.product: Windows 10 or later.
---

# DOT11_WPS_DEVICE_NAME structure



## -description

## -syntax

````
typedef struct _DOT11_WPS_DEVICE_NAME {
   ULONG  
uDeviceNameLength;
  UCHAR   ucDeviceName[DOT11_WPS_DEVICE_NAME_MAX_LENGTH];
} DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME;
````


## -struct-fields
<dl>

### -field <b>
uDeviceNameLength</b>

<dd>
<p>The length, in bytes, of the device name.</p>
</dd>

### -field <b>ucDeviceName[DOT11_WPS_DEVICE_NAME_MAX_LENGTH]</b>

<dd>
<p>A UTF-8–encoded descriptive name of the device.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with   Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>