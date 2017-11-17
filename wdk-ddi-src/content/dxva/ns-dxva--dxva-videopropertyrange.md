---
UID: NS.dxva._DXVA_VideoPropertyRange
title: DXVA_VideoPropertyRange
author: windows-driver-content
description: The DXVA_VideoPropertyRange structure specifies the range of allowed values for ProcAmp control properties.
old-location: display\dxva_videopropertyrange.htm
ms.assetid: e78fa9ba-7573-47db-b4d8-9b7584d5b432
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_VideoPropertyRange
req.alt-loc: dxva.h
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
ms.keywords: DXVA_VideoPropertyRange, DXVA_VideoPropertyRange, *LPDXVA_VideoPropertyRange
req.iface: 
---

# DXVA_VideoPropertyRange structure



## -description
<p>The DXVA_VideoPropertyRange structure specifies the range of allowed values for ProcAmp control properties.</p>


## -syntax

````
typedef struct _DXVA_VideoPropertyRange {
  FLOAT MinValue;
  FLOAT MaxValue;
  FLOAT DefaultValue;
  FLOAT StepSize;
} DXVA_VideoPropertyRange, *LPDXVA_VideoPropertyRange;
````


## -struct-fields
<dl>

### -field <b>MinValue</b>

<dd>
<p>Specifies the minimum value allowed for a given property.</p>
</dd>

### -field <b>MaxValue</b>

<dd>
<p>Specifies the maximum value allowed for a given property.</p>
</dd>

### -field <b>DefaultValue</b>

<dd>
<p>Specifies the default value for a given property.</p>
</dd>

### -field <b>StepSize</b>

<dd>
<p>Specifies the step size increment for a given property.</p>
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
<p>DirectX 9.0 and later versions only.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564070">DXVA_VideoDesc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoPropertyRange structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>