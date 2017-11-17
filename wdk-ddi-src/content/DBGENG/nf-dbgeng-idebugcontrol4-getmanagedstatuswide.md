---
UID: NF.dbgeng.IDebugControl4.GetManagedStatusWide
title: IDebugControl4::GetManagedStatusWide
author: windows-driver-content
description: Provides feedback as a Unicode character string on the engine's use of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_getmanagedstatuswide.htm
ms.assetid: 5854BB6A-EB5F-493A-96E4-0DF298EC0332
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl4.GetManagedStatusWide
req.alt-loc: dbgeng.h
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
ms.keywords: IDebugControl4, GetManagedStatusWide, IDebugControl4::GetManagedStatusWide
req.iface: IDebugControl4
---

# IDebugControl4::GetManagedStatusWide method



## -description
<p> Provides feedback as a Unicode character string on the engine's
    use of the runtime debugging APIs provided by the common language runtime (CLR).</p>


## -syntax

````
HRESULT GetManagedStatusWide(
  [out, optional] PULONG                         Flags,
  [in]            ULONG                          WhichString,
  [out]           _writes_opt_(StringSize) PWSTR String,
  [in]            ULONG                          StringSize,
  [out, optional] PULONG                         StringNeeded
);
````


## -parameters
<dl>

### -param <i>Flags</i> [out, optional]

<dd>
<p>A pointer to flags from the debugging APIs.</p>
</dd>

### -param <i>WhichString</i> [in]

<dd>
<p>A value that controls which string to use.</p>
</dd>

### -param <i>String</i> [out]

<dd>
<p>A pointer to a Unicode character string from the debugging APIs.</p>
</dd>

### -param <i>StringSize</i> [in]

<dd>
<p>The size of the string.</p>
</dd>

### -param <i>StringNeeded</i> [out, optional]

<dd>
<p>A pointer to an output string.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>    Managed debugging support relies on debugging
    functionality provided by the CLR.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetManagedStatusWide method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>