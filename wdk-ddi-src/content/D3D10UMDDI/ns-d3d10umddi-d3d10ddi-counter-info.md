---
UID: NS.d3d10umddi.D3D10DDI_COUNTER_INFO
title: D3D10DDI_COUNTER_INFO
author: windows-driver-content
description: The D3D10DDI_COUNTER_INFO structure describes information to manipulate counters.
old-location: display\d3d10ddi_counter_info.htm
ms.assetid: fda3d4a2-4c1a-454d-bcb0-4174699c5bb8
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDI_COUNTER_INFO
req.alt-loc: d3d10umddi.h
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
ms.keywords: D3D10DDI_COUNTER_INFO, D3D10DDI_COUNTER_INFO
req.iface: 
---

# D3D10DDI_COUNTER_INFO structure



## -description
<p>The D3D10DDI_COUNTER_INFO structure describes information to manipulate counters.</p>


## -syntax

````
typedef struct D3D10DDI_COUNTER_INFO {
  D3D10DDI_QUERY LastDeviceDependentCounter;
  UINT           NumSimultaneousCounters;
  UINT8          NumDetectableParallelUnits;
} D3D10DDI_COUNTER_INFO;
````


## -struct-fields
<dl>

### -field <b>LastDeviceDependentCounter</b>

<dd>
<p>[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>-typed value that identifies the largest device-dependent counter identifier that the device supports. If none are supported, the user-mode display driver must set the value to 0; otherwise, the driver sets the value to greater than or equal to D3D10DDI_COUNTER_DEVICE_DEPENDENT_0 (0x40000000). </p>
</dd>

### -field <b>NumSimultaneousCounters</b>

<dd>
<p>[out] The number of simultaneously active counters that the driver supports. </p>
</dd>

### -field <b>NumDetectableParallelUnits</b>

<dd>
<p>[out] The number of detectable parallel units that the counters can identify. Valid values are from 1 through 4.</p>
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
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDI_COUNTER_INFO structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>