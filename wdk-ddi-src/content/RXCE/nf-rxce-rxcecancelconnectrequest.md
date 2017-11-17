---
UID: NF.rxce.RxCeCancelConnectRequest
title: RxCeCancelConnectRequest
author: windows-driver-content
description: RxCeCancelConnectRequest cancels a previously issued connection request. Note that this routine is not currently implemented.
old-location: ifsk\rxcecancelconnectrequest.htm
ms.assetid: 32893a68-68ac-4bac-ab0f-1d07a1e873f3
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxCeCancelConnectRequest
req.alt-loc: rxce.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
ms.keywords: RxCeCancelConnectRequest
req.iface: 
req.product: Windows 10 or later.
---

# RxCeCancelConnectRequest function



## -description
<p><b>RxCeCancelConnectRequest</b> cancels a previously issued connection request. Note that this routine is not currently implemented.</p>


## -syntax

````
NTSTATUS RxCeCancelConnectRequest(
  _In_ PRXCE_ADDRESS                pLocalAddress,
  _In_ PUNICODE_STRING              pServerName,
  _In_ PRXCE_CONNECTION_INFORMATION pConnectionInformation
);
````


## -parameters
<dl>

### -param <i>pLocalAddress</i> [in]

<dd>
<p>A pointer to the local RDBSS connection engine address on which the previously issued connection request was made.</p>
</dd>

### -param <i>pServerName</i> [in]

<dd>
<p>A pointer to the name of the server on which the previous connection request was made.</p>
</dd>

### -param <i>pConnectionInformation</i> [in]

<dd>
<p>A pointer to the connection information that specifies the remote address. on which the previously issued connection request was made.</p>
</dd>
</dl>

## -returns
<p><b>RxCeCancelConnectRequest</b> returns STATUS_NOT_IMPLEMENTED since this routine is not currently implemented.</p>

## -remarks
<p><b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. </p>

<p><b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rxce.h (include Rxce.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554321">RxCeTearDownConnection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565085">TDI_CONNECTION_INFORMATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeCancelConnectRequest routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>