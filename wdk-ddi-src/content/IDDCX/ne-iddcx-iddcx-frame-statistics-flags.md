---
UID: NE.iddcx.IDDCX_FRAME_STATISTICS_FLAGS
title: IDDCX_FRAME_STATISTICS_FLAGS
author: windows-driver-content
description: Indicates whether a frame was altered by the driver.
old-location: display\iddcx_frame_statistics_flags.htm
ms.assetid: 85ae47d8-228c-4fff-9be0-bf56868b9319
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: display
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDDCX_FRAME_STATISTICS_FLAGS
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
ms.keywords: WcsTranslateColors
req.iface: 
---

# IDDCX_FRAME_STATISTICS_FLAGS enumeration



## -description
<p>
                    
                Indicates whether a frame was altered by the driver.</p>


## -syntax

````
typedef enum _IDDCX_FRAME_STATISTICS_FLAGS { 
  IDDCX_FRAME_STATISTICS_FLAGS_NONE                    = 0,
  IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY  = 1
} IDDCX_FRAME_STATISTICS_FLAGS;
````


## -enum-fields
<dl>

### -field <a id="IDDCX_FRAME_STATISTICS_FLAGS_NONE"></a><a id="iddcx_frame_statistics_flags_none"></a><b>IDDCX_FRAME_STATISTICS_FLAGS_NONE</b>

<dd>
<p>
                        
                    Indicates that there are no alterations to the frame.</p>
</dd>

### -field <a id="IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY"></a><a id="iddcx_frame_statistics_flags_reduced_color_fidelity"></a><b>IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY</b>

<dd>
<p>
                        If set indicates that the driver reduced the color fidelity of the desktop image while processing and transmitting this frame.</p>
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
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>