---
UID: NE.nfccx._NFC_CX_CE_MODE_CONFIG
title: NFC_CX_CE_MODE_CONFIG
author: windows-driver-content
description: This enumeration specifies CE listening mode flags.
old-location: nfpdrivers\nfc_cx_ce_mode_config.htm
ms.assetid: 2C7071A4-B978-408C-9C98-67BC63F2BBCA
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: nfpdrivers
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NFC_CX_CE_MODE_CONFIG, *PNFC_CX_CE_MODE_CONFIG
req.alt-loc: nfccx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Requires same
ms.keywords: NPI_REGISTRATION_INSTANCE, NPI_REGISTRATION_INSTANCE
req.iface: 
---

# NFC_CX_CE_MODE_CONFIG enumeration



## -description
<p>This enumeration specifies CE listening mode flags.</p>


## -syntax

````
typedef enum _NFC_CX_CE_MODE_CONFIG { 
  NFC_CX_CE_NFC_A    = 0x01,
  NFC_CX_CE_NFC_B    = 0x02,
  NFC_CX_CE_NFC_F    = 0x04,
  NFC_CX_CE_DEFAULT  = NFC_CX_CE_NFC_A | NFC_CX_CE_NFC_B | NFC_CX_CE_NFC_F
} NFC_CX_CE_MODE_CONFIG, *PNFC_CX_CE_MODE_CONFIG;
````


## -enum-fields
<dl>

### -field <a id="NFC_CX_CE_NFC_A"></a><a id="nfc_cx_ce_nfc_a"></a><b>NFC_CX_CE_NFC_A</b>

<dd>
<p>Specifies NFC-A listening mode.</p>
</dd>

### -field <a id="NFC_CX_CE_NFC_B"></a><a id="nfc_cx_ce_nfc_b"></a><b>NFC_CX_CE_NFC_B</b>

<dd>
<p>Specifies NFC-B listening mode.</p>
</dd>

### -field <a id="NFC_CX_CE_NFC_F"></a><a id="nfc_cx_ce_nfc_f"></a><b>NFC_CX_CE_NFC_F</b>

<dd>
<p>Specifies NFC-F listening mode.</p>
</dd>

### -field <a id="NFC_CX_CE_DEFAULT"></a><a id="nfc_cx_ce_default"></a><b>NFC_CX_CE_DEFAULT</b>

<dd>
<p>Specifies NFC-A, NFC-B, and NFC-F listening mode.</p>
</dd>
</dl>

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
<p>None supported</p>
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
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_CE_MODE_CONFIG enumeration%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>