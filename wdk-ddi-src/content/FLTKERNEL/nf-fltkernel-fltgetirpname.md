---
UID: NF.fltkernel.FltGetIrpName
title: FltGetIrpName
author: windows-driver-content
description: The FltGetIrpName routine returns the name for a major function code as a printable string.
old-location: ifsk\fltgetirpname.htm
ms.assetid: d4087825-cdfd-4de5-a5b7-f95f6f0563e6
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetIrpName
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: Any level
ms.keywords: FltGetIrpName
req.iface: 
---

# FltGetIrpName function



## -description
<p>The <b>FltGetIrpName</b> routine returns the name for a major function code as a printable string. </p>


## -syntax

````
PCHAR FltGetIrpName(
  _In_ UCHAR IrpMajorCode
);
````


## -parameters
<dl>

### -param <i>IrpMajorCode</i> [in]

<dd>
<p>The IRP major function code whose name is to be returned. </p>
</dd>
</dl>

## -returns
<p>If <i>IrpMajorCode</i> is a valid major function code value, <b>FltGetIrpName</b> returns its name as a null-terminated string of ANSI characters (such as "IRP_MJ_CREATE"). Otherwise, <b>FltGetIrpName</b> returns "&lt;invalid IRP code&gt;". </p>

## -remarks
<p><b>FltGetIrpName</b> is a debugging support routine. </p>

<p>The value of the <i>IrpMajorCode</i> parameter can equal to the value of the <b>MajorFunction</b> field for an IRP or the <b>MajorFunction</b> field for the <b>Iopb</b> field of a callback data structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). </p>

<p><b>FltGetIrpName</b> is a debugging support routine. </p>

<p>The value of the <i>IrpMajorCode</i> parameter can equal to the value of the <b>MajorFunction</b> field for an IRP or the <b>MajorFunction</b> field for the <b>Iopb</b> field of a callback data structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetIrpName routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>