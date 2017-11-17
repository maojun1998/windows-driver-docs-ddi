---
UID: NE.ksmedia.KS_AMPixAspectRatio
title: KS_AMPixAspectRatio
author: windows-driver-content
description: The KS_AMPixAspectRatio enumeration defines the pixel aspect ratio that corresponds to a 720 480 NTSC video signal or a 720 × 576 PAL video signal.
old-location: stream\ks_ampixaspectratio.htm
ms.assetid: 29c84529-11f6-429b-81c6-96d6a1773b3b
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: stream
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_AMPixAspectRatio
req.alt-loc: ksmedia.h
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
ms.keywords: PKSIDEFAULTCLOCK, KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
req.iface: 
---

# KS_AMPixAspectRatio enumeration



## -description
<p>The KS_AMPixAspectRatio enumeration defines the pixel aspect ratio that corresponds to a 720  480 NTSC video signal or a 720 × 576 PAL video signal.</p>


## -syntax

````
typedef enum  { 
  KS_PixAspectRatio_NTSC4x3   = 0,
  KS_PixAspectRatio_NTSC16x9  = 1,
  KS_PixAspectRatio_PAL4x3    = 2,
  KS_PixAspectRatio_PAL16x9   = 3
} KS_AMPixAspectRatio;
````


## -enum-fields
<dl>

### -field <a id="KS_PixAspectRatio_NTSC4x3"></a><a id="ks_pixaspectratio_ntsc4x3"></a><a id="KS_PIXASPECTRATIO_NTSC4X3"></a><b>KS_PixAspectRatio_NTSC4x3</b>

<dd>
<p>Specifies a 4 × 3 NTSC pixel aspect ratio.</p>
</dd>

### -field <a id="KS_PixAspectRatio_NTSC16x9"></a><a id="ks_pixaspectratio_ntsc16x9"></a><a id="KS_PIXASPECTRATIO_NTSC16X9"></a><b>KS_PixAspectRatio_NTSC16x9</b>

<dd>
<p>Specifies a 16 × 9 NTSC pixel aspect ratio.</p>
</dd>

### -field <a id="KS_PixAspectRatio_PAL4x3"></a><a id="ks_pixaspectratio_pal4x3"></a><a id="KS_PIXASPECTRATIO_PAL4X3"></a><b>KS_PixAspectRatio_PAL4x3</b>

<dd>
<p>Specifies a 4 × 3 PAL pixel aspect ratio.</p>
</dd>

### -field <a id="KS_PixAspectRatio_PAL16x9"></a><a id="ks_pixaspectratio_pal16x9"></a><a id="KS_PIXASPECTRATIO_PAL16X9"></a><b>KS_PixAspectRatio_PAL16x9</b>

<dd>
<p>Specifies a 16 × 9 PAL pixel aspect ratio.</p>
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
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>