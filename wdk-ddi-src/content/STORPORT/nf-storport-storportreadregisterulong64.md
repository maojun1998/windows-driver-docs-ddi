---
UID: NF.storport.StorPortReadRegisterUlong64
title: StorPortReadRegisterUlong64
author: windows-driver-content
description: The StorPortReadRegisterUlong64 routine reads a 64-bit value from a specified 64-bit register address.
old-location: storage\storportreadregisterulong64.htm
ms.assetid: 73A9E645-0B71-429F-9033-032BB83E60E4
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortReadRegisterUlong64
req.alt-loc: storport.h
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
ms.keywords: StorPortReadRegisterUlong64
req.iface: 
req.product: Windows 10 or later.
---

# StorPortReadRegisterUlong64 function



## -description
<p>The <b>StorPortReadRegisterUlong64</b> routine reads a 64-bit value from a specified 64-bit register address.</p>


## -syntax

````
 VOID StorPortReadRegisterUlong64(
  _In_ PULONG64  Register
);
````


## -parameters
<dl>

### -param <i>Register</i> [in]

<dd>
<p>Pointer to the register where the data is to be read. </p>
</dd>
</dl>

## -returns
<p>This routine does not return a value.</p>

## -remarks
<p>The <b>StorPortReadRegisterUlong64</b> routine is only available on the 64-bit version of Windows.</p>

<p>The <b>StorPortReadRegisterUlong64</b> routine is only available on the 64-bit version of Windows.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh967743">StorPortWriteRegisterUlong64</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20StorPortReadRegisterUlong64 routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>