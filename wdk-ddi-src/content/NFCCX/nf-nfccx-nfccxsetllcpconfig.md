---
UID: NF.nfccx.NfcCxSetLlcpConfig
title: NfcCxSetLlcpConfig
author: windows-driver-content
description: Called by the client driver to configure the LLCP parameters.
old-location: nfpdrivers\_nfccxsetllcpconfig.htm
ms.assetid: 8208F61E-DFD9-4AA8-B225-BEB35F80F621
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: nfpdrivers
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NfcCxSetLlcpConfig
req.alt-loc: NfcCx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nfccxstub.lib
req.dll: NfcCx.dll
req.irql: 
ms.keywords: NfcCxSetLlcpConfig
req.iface: 
---

# NfcCxSetLlcpConfig function



## -description
<p>Called by the client driver to configure the LLCP parameters.</p>


## -syntax

````
NTSTATUS NfcCxSetLlcpConfig(
   WDFDEVICE            Device,
   PCNFC_CX_LLCP_CONFIG Config
);
````


## -parameters
<dl>

### -param <i>Device</i> 

<dd>
<p>A handle to a framework device object.</p>
</dd>

### -param <i>Config</i> 

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn905545">NFC_CX_LLCP_CONFIG</a> structure.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function returns STATUS_SUCCESS.</p>

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
<dt>Nfccx.h (include Ncidef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Nfccxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NfcCx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxSetLlcpConfig method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>