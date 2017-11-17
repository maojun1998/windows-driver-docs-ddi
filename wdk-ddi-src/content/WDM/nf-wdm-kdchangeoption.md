---
UID: NF.wdm.KdChangeOption
title: KdChangeOption
author: windows-driver-content
description: The KdChangeOption routine accesses and changes state in the kernel that is related to kernel debugging.
old-location: devtest\kdchangeoption.htm
ms.assetid: 6f93b62b-6dc2-417b-9e1c-44be628c489c
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: devtest
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows and Windows Server.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KdChangeOption
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
ms.keywords: KdChangeOption
req.iface: 
req.product: Windows 10 or later.
---

# KdChangeOption function



## -description
<p>The <b>KdChangeOption</b> routine accesses and changes state in the kernel that is related to kernel debugging. </p>


## -syntax

````
NTSTATUS KdChangeOption(
  _In_      KD_OPTION Option,
  _In_opt_  ULONG     InBufferBytes,
  _In_      PVOID     InBuffer,
  _In_opt_  ULONG     OutBufferBytes,
  _Out_     PVOID     OutBuffer,
  _Out_opt_ PULONG    OutBufferNeeded
);
````


## -parameters
<dl>

### -param <i>Option</i> [in]

<dd>
<p>A value from the KD_OPTION enumeration that indicates the kernel state to access and change. The value of this parameter determines the format and required length of the <i>InBuffer</i> and <i>OutBuffer</i>. Currently, the only valid value is KD_OPTION_SET_BLOCK_ENABLE. </p>
</dd>

### -param <i>InBufferBytes</i> [in, optional]

<dd>
<p>The size, in bytes, of the buffer at <i>InBuffer</i>. This value is optional. </p>
</dd>

### -param <i>InBuffer</i> [in]

<dd>
<p>A pointer to a caller-allocated input buffer that contains information about the kernel state to change. If <i>Option</i> specifies a kernel state that does not require input data, this pointer can be <b>NULL</b>.</p>
</dd>

### -param <i>OutBufferBytes</i> [in, optional]

<dd>
<p>The size, in bytes, of the buffer at <i>OutBuffer</i>. This value is optional.</p>
</dd>

### -param <i>OutBuffer</i> [out]

<dd>
<p>A pointer to a caller-allocated output buffer in which information that pertains to the kernel state is returned. If <i>Option</i> specifies a kernel state that does not produce output data, this pointer can be <b>NULL</b>. </p>
</dd>

### -param <i>OutBufferNeeded</i> [out, optional]

<dd>
<p>A pointer to a variable that receives the size, in bytes, of the required output buffer at <i>OutBuffer</i>. This value is optional.</p>
</dd>
</dl>

## -returns
<p><b>KdChangeOption</b> returns STATUS_SUCCESS if it successfully carried out the requested operation. Otherwise, the return value can be one of the following error status codes: </p>

<p>STATUS_ACCESS_DENIED</p>

<p>STATUS_INVALID_INFO_CLASS</p>

<p>STATUS_INVALID_PARAMETER</p>

<p>STATUS_DEBUGGER_INACTIVE</p>

## -remarks
<p>If the operating system was booted with no debug controls, <b>KdChangeOption</b> returns STATUS_DEBUGGER_INACTIVE.</p>

<p>Currently, the only valid value for the <i>Option</i> parameter is KD_OPTION_SET_BLOCK_ENABLE. If <i>Option</i> is set to any other value, <b>KdChangeOption</b> returns STATUS_INVALID_INFO_CLASS. When <i>Option</i> is KD_OPTION_SET_BLOCK_ENABLE, the caller must set the <i>InBufferBytes</i> parameter to <b>sizeof</b>(BOOLEAN), the <i>OutBufferBytes</i> parameter to zero, and the <i>OutBuffer</i> parameter to <b>NULL</b>; otherwise, <b>KdChangeOption</b> returns STATUS_INVALID_PARAMETER. If the high bit (0x80) in the <b>KdBlockEnable</b> system variable is set to one, the debugger can never be re-enabled, and <b>KdChangeOption</b> returns STATUS_ACCESS_DENIED. Otherwise, <b>KdChangeOption</b> sets the <b>KdBlockEnable</b> system variable to the BOOLEAN value that <i>InBuffer</i> points to.</p>

<p>If the operating system was booted with no debug controls, <b>KdChangeOption</b> returns STATUS_DEBUGGER_INACTIVE.</p>

<p>Currently, the only valid value for the <i>Option</i> parameter is KD_OPTION_SET_BLOCK_ENABLE. If <i>Option</i> is set to any other value, <b>KdChangeOption</b> returns STATUS_INVALID_INFO_CLASS. When <i>Option</i> is KD_OPTION_SET_BLOCK_ENABLE, the caller must set the <i>InBufferBytes</i> parameter to <b>sizeof</b>(BOOLEAN), the <i>OutBufferBytes</i> parameter to zero, and the <i>OutBuffer</i> parameter to <b>NULL</b>; otherwise, <b>KdChangeOption</b> returns STATUS_INVALID_PARAMETER. If the high bit (0x80) in the <b>KdBlockEnable</b> system variable is set to one, the debugger can never be re-enabled, and <b>KdChangeOption</b> returns STATUS_ACCESS_DENIED. Otherwise, <b>KdChangeOption</b> sets the <b>KdBlockEnable</b> system variable to the BOOLEAN value that <i>InBuffer</i> points to.</p>

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
<p>Available in Microsoft Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows and Windows Server.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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