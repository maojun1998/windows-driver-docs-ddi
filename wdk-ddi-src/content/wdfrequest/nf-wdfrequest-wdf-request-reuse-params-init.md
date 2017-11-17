---
UID: NF.wdfrequest.WDF_REQUEST_REUSE_PARAMS_INIT
title: WDF_REQUEST_REUSE_PARAMS_INIT
author: windows-driver-content
description: The WDF_REQUEST_REUSE_PARAMS_INIT function initializes a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_params_init.htm
ms.assetid: a77d77c5-5c8a-439a-93a3-fe29b15c6ed0
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_REQUEST_REUSE_PARAMS_INIT
req.alt-loc: wdfrequest.h
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
ms.keywords: WDF_REQUEST_REUSE_PARAMS_INIT
req.iface: 
req.product: Windows 10 or later.
---

# WDF_REQUEST_REUSE_PARAMS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.</p>


## -syntax

````
VOID WDF_REQUEST_REUSE_PARAMS_INIT(
  _Out_ PWDF_REQUEST_REUSE_PARAMS Params,
  _In_  ULONG                     Flags,
  _In_  NTSTATUS                  Status
);
````


## -parameters
<dl>

### -param <i>Params</i> [out]

<dd>
<p>A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.</p>
</dd>

### -param <i>Flags</i> [in]

<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552477">WDF_REQUEST_REUSE_FLAGS</a>-typed flags. </p>
</dd>

### -param <i>Status</i> [in]

<dd>
<p>An NTSTATUS value that the framework assigns to the request.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Before a driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a> method, it must call <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.</p>

<p>The <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure and sets the structures <b>Size</b> member. It also sets the structure's <b>Flags</b> and <b>Status</b> members to the specified values.</p>

<p>For a code example that uses <b>WDF_REQUEST_REUSE_PARAMS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>.</p>

<p>Before a driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a> method, it must call <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.</p>

<p>The <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure and sets the structures <b>Size</b> member. It also sets the structure's <b>Flags</b> and <b>Status</b> members to the specified values.</p>

<p>For a code example that uses <b>WDF_REQUEST_REUSE_PARAMS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfrequest.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552487">WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_REUSE_PARAMS_INIT function%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>