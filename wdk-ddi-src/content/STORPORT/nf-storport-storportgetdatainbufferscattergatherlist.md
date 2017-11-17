---
UID: NF.storport.StorPortGetDataInBufferScatterGatherList
title: StorPortGetDataInBufferScatterGatherList
author: windows-driver-content
description: Returns the scatter-gather list associated with the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbufferscattergatherlist.htm
ms.assetid: 015592AE-4AF6-48C8-BF79-6B22A6FCAB98
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
req.alt-api: StorPortGetDataInBufferScatterGatherList
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: Any
ms.keywords: StorPortGetDataInBufferScatterGatherList
req.iface: 
req.product: Windows 10 or later.
---

# StorPortGetDataInBufferScatterGatherList function



## -description
<p>Returns the scatter-gather list associated with the input data buffer  of a SCSI request block (SRB).</p>


## -syntax

````
ULONG StorPortGetDataInBufferScatterGatherList(
  _In_  PVOID                     HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK       Srb,
  _Out_ PSTOR_SCATTER_GATHER_LIST *SgList
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>A pointer to the hardware device extension for the host bus adapter (HBA).</p>
</dd>

### -param <i>Srb</i> [in]

<dd>
<p>The request block to containing the input data buffer for the scatter-gather list.</p>
</dd>

### -param <i>SgList</i> [out]

<dd>
<p>A pointer to  an scatter-gather list structure address to receive the scatter-gather list for the input data buffer in <i>Srb</i>.</p>
</dd>
</dl>

## -returns
<p>A status value indicating the result of the notification. This can be one of these values:</p><dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl><p>The scatter-gather list for <i>Srb</i> was successfully returned.</p><dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The pointer value in <i>SgList</i> is NULL.</p>

<p> </p>

## -remarks


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
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj553718">StorPortGetDataInBufferMdl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj553720">StorPortGetDataInBufferSystemAddress</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20StorPortGetDataInBufferScatterGatherList routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>