---
UID: NS.ufxclient._UFX_ENDPOINT_CALLBACKS
title: UFX_ENDPOINT_CALLBACKS
author: windows-driver-content
description: The UFX_ENDPOINT_CALLBACKS structure is used to define then event callback functions supported by the client driver.
old-location: buses\ufx_endpoint_callbacks.htm
ms.assetid: CED05E15-E141-4A6D-A657-CF0DF9FD1200
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: usbref
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFX_ENDPOINT_CALLBACKS
req.alt-loc: ufxclient.h
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
ms.keywords: UFX_ENDPOINT_CALLBACKS, UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
req.iface: 
req.product: Windows 10 or later.
---

# UFX_ENDPOINT_CALLBACKS structure



## -description
<p>The <b>UFX_ENDPOINT_CALLBACKS</b> structure is used to define then event callback functions supported by the client driver. </p>


## -syntax

````
typedef struct _UFX_ENDPOINT_CALLBACKS {
  ULONG Size;
} UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The size of the <b>UFX_ENDPOINT_CALLBACKS</b>         structure.</p>
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
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
</table>