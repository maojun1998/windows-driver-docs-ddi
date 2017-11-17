---
UID: NS.d3dumddi._D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL
title: D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL
author: windows-driver-content
description: The D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure describes the state that is set within an authenticated channel by using the ConfigureAuthenticatedChannel function.
old-location: display\d3dddiarg_configureauthenticatedchannel.htm
ms.assetid: 8f27fe6d-fe34-4006-a8b1-d2f2190ec044
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL
req.alt-loc: d3dumddi.h
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
ms.keywords: D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL, D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL
req.iface: 
---

# D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL structure



## -description
<p>The D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure describes the state that is set within an authenticated channel by using the <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> function. </p>


## -syntax

````
typedef struct _D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL {
  UINT       InputSize;
  const VOID *pInputData;
  VOID       *pOutputData;
} D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL;
````


## -struct-fields
<dl>

### -field <b>InputSize</b>

<dd>
<p>[in] The size, in bytes, of the input data that the <b>pInputData</b> member points to. </p>
</dd>

### -field <b>pInputData</b>

<dd>
<p>[in] A pointer to a buffer that describes the configuration data to set. The definition of the input buffer depends on the configuration data that is set. The buffer that <b>pInputData</b> points to is defined identically to the input buffer that is passed to the <b>IDirect3DAuthenticatedChannel::Configure</b> method. For more information about <b>IDirect3DAuthenticatedChannel::Configure</b>, see the Windows SDK documentation. </p>
</dd>

### -field <b>pOutputData</b>

<dd>
<p>[in/out] A pointer to a buffer that describes the information that the <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> function returns. </p>
</dd>
</dl>

## -remarks
<p>The first member of the input buffer that the <b>pInputData</b> member points to is always the D3DAUTHENTICATEDCHANNEL_CONFIGURE_INPUT structure, whose members specify the following information: </p>

<p>The <b>ConfigureType</b> member identifies the configuration state to set. </p>

<p>The <b>omac</b> member identifies the One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC), which verifies that the input is from a trusted source.</p>

<p>The <b>SequenceNumber</b> member specifies a unique number that the driver can use to prevent against replay attacks. </p>

<p>The <b>pOutputData</b> member points to a D3DAUTHENTICATEDCHANNEL_CONFIGURE_OUTPUT structure that contains the configuration type and the sequence number of the output buffer to prevent against replay attacks. </p>

<p>Configuration state that an authenticated channel sets cannot be disabled by another authenticated channel. A call to the driver's <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> function with such an attempt   fails. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>