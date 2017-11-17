---
UID: NS.aux_klib._AUX_MODULE_BASIC_INFO
title: AUX_MODULE_BASIC_INFO
author: windows-driver-content
description: The AUX_MODULE_BASIC_INFO structure contains basic information about a loaded image module.
old-location: kernel\aux_module_basic_info.htm
ms.assetid: 8cee85a3-b2e4-4378-a700-862d1b517f14
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AUX_MODULE_BASIC_INFO
req.alt-loc: aux_klib.h
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
ms.keywords: AUX_MODULE_BASIC_INFO, AUX_MODULE_BASIC_INFO, *PAUX_MODULE_BASIC_INFO
req.iface: 
---

# AUX_MODULE_BASIC_INFO structure



## -description
<p>The <b>AUX_MODULE_BASIC_INFO</b> structure contains basic information about a loaded image module.</p>


## -syntax

````
typedef struct _AUX_MODULE_BASIC_INFO {
  PVOID ImageBase;
} AUX_MODULE_BASIC_INFO, *PAUX_MODULE_BASIC_INFO;
````


## -struct-fields
<dl>

### -field <b>ImageBase</b>

<dd>
<p>A pointer to the base of the loaded image. </p>
</dd>
</dl>

## -remarks
<p>The <b>AUX_MODULE_BASIC_INFO</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a> routine.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Aux_klib.h (include Aux_klib.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AUX_MODULE_BASIC_INFO structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>