---
UID: NF.dbgeng.IDebugSymbols4.GetNameByInlineContext
title: IDebugSymbols4::GetNameByInlineContext
author: windows-driver-content
description: Gets a name by inline context.
old-location: debugger\idebugsymbols4_getnamebyinlinecontext.htm
ms.assetid: C87E70ED-FCB0-47B6-B6A3-A8EBC8E84058
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
req.alt-api: IDebugSymbols4.GetNameByInlineContext
req.alt-loc: Dbgeng.h
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
ms.keywords: IDebugSymbols4, GetNameByInlineContext, IDebugSymbols4::GetNameByInlineContext
req.iface: IDebugSymbols4
---

# IDebugSymbols4::GetNameByInlineContext method



## -description
<p>Gets a name by inline context.</p>


## -syntax

````
HRESULT GetNameByInlineContext(
  [in]            ULONG64                           Offset,
  [in]            ULONG                             InlineContext,
  [out]           _writes_opt_(NameBufferSize) PSTR NameBuffer,
  [in]            ULONG                             NameBufferSize,
  [out, optional] PULONG                            NameSize,
  [out, optional] PULONG64                          Displacement
);
````


## -parameters
<dl>

### -param <i>Offset</i> [in]

<dd>
<p>An offset for the name.</p>
</dd>

### -param <i>InlineContext</i> [in]

<dd>
<p>The inline context.</p>
</dd>

### -param <i>NameBuffer</i> [out]

<dd>
<p>A pointer an output buffer.</p>
</dd>

### -param <i>NameBufferSize</i> [in]

<dd>
<p>The size of the name buffer.</p>
</dd>

### -param <i>NameSize</i> [out, optional]

<dd>
<p>A pointer to the length of the name.</p>
</dd>

### -param <i>Displacement</i> [out, optional]

<dd>
<p>A pointer to the displacement value of the name.</p>
</dd>
</dl>

## -returns
<p>If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.</p>

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
<a href="https://msdn.microsoft.com/BE2734B5-1E67-4E38-B4DF-0C353BFB1F0B">IDebugSymbols4</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols4::GetNameByInlineContext method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>