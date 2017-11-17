---
UID: NF.bthhfpddi.BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
title: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
author: windows-driver-content
description: The BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT method returns a pointer to an initialized BTHHFP_AUDIO_DEVICE_CAPABILTIES data structure.
old-location: audio\bthhfp_audio_device_capabilties_init.htm
ms.assetid: c00b8f19-6708-4ec2-928b-610158850247
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: audio
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
req.alt-loc: bthhfpddi.h
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
ms.keywords: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
req.iface: 
---

# BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT function



## -description
<p>The 
			
            <b>BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT</b> method returns a pointer to an initialized <a href="audio._bthhfp_audio_device_capabilties">BTHHFP_AUDIO_DEVICE_CAPABILTIES</a> data structure. </p>


## -syntax

````
FORCEINLINE VOID  BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT(
  _Out_ PBTHHFP_AUDIO_DEVICE_CAPABILTIES caps
);
````


## -parameters
<dl>

### -param <i>caps</i> [out]

<dd>
<p>A pointer to an initialized <a href="audio._bthhfp_audio_device_capabilties">BTHHFP_AUDIO_DEVICE_CAPABILTIES</a> data structure.</p>
</dd>
</dl>

## -returns
<p>This method does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bthhfpddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p></p>
</td>
</tr>
</table>