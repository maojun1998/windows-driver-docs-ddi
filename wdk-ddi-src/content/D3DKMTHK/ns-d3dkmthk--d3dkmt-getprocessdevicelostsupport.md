---
UID: NS.d3dkmthk._D3DKMT_GETPROCESSDEVICELOSTSUPPORT
title: D3DKMT_GETPROCESSDEVICELOSTSUPPORT
author: windows-driver-content
description: Used to get the indicated process.
old-location: display\d3dkmt-getprocessdevicelostsupport.htm
ms.assetid: 726a4f12-3cee-4d95-89d3-39f2bb357967
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_GETPROCESSDEVICELOSTSUPPORT
req.alt-loc: d3dkmthk.h
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
ms.keywords: D3DKMT_GETPROCESSDEVICELOSTSUPPORT, D3DKMT_GETPROCESSDEVICELOSTSUPPORT
req.iface: 
---

# D3DKMT_GETPROCESSDEVICELOSTSUPPORT structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>Used to get the indicated process.</p>


## -syntax

````
typedef struct _D3DKMT_GETPROCESSDEVICELOSTSUPPORT {
  HANDLE  hProcess;
  LUID    AdapterLuid;
  BOOLEAN Support;
} D3DKMT_GETPROCESSDEVICELOSTSUPPORT;
````


## -struct-fields
<dl>

### -field <b>hProcess</b>

<dd>
<p>A handle to the process.</p>
</dd>

### -field <b>AdapterLuid</b>

<dd>
<p>LUID of Adapter that is potentially being detached</p>
</dd>

### -field <b>Support</b>

<dd>
<p>Indicates whether or not all devices of the process using the adapter can recover from graphics device lost.</p>
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
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>