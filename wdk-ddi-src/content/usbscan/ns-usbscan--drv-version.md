---
UID: NS.usbscan._DRV_VERSION
title: DRV_VERSION
author: windows-driver-content
description: The DRV_VERSION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_VERSION.
old-location: image\drv_version.htm
ms.assetid: 61b6dbd3-7565-4d63-bcc0-007df9793398
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: image
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRV_VERSION
req.alt-loc: usbscan.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: DRV_VERSION, DRV_VERSION, *PDRV_VERSION
req.iface: 
req.product: Windows 10 or later.
---

# DRV_VERSION structure



## -description
<p>The DRV_VERSION structure is used as a parameter to <a href="base.deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff542866">IOCTL_GET_VERSION</a>.</p>


## -syntax

````
typedef struct _DRV_VERSION {
  unsigned major;
  unsigned minor;
  unsigned internal;
} DRV_VERSION, *PDRV_VERSION;
````


## -struct-fields
<dl>

### -field <b>major</b>

<dd>
<p>Major version number.</p>
</dd>

### -field <b>minor</b>

<dd>
<p>Minor version number.</p>
</dd>

### -field <b>internal</b>

<dd>
<p>Internal, vendor-specific version number.</p>
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
<dt>Usbscan.h (include Usbscan.h)</dt>
</dl>
</td>
</tr>
</table>