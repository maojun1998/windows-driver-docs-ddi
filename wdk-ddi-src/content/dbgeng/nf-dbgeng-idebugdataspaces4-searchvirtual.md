---
UID: NF.dbgeng.IDebugDataSpaces4.SearchVirtual
title: IDebugDataSpaces4::SearchVirtual method
author: windows-driver-content
description: The SearchVirtual method searches the target's virtual memory for a specified pattern of bytes.
old-location: debugger\searchvirtual.htm
old-project: Debugger
ms.assetid: 1cb779de-fcbb-450d-9932-0cdaa9fbb1e9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::SearchVirtual, SearchVirtual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces.SearchVirtual,IDebugDataSpaces2.SearchVirtual,IDebugDataSpaces3.SearchVirtual,IDebugDataSpaces4.SearchVirtual
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
---

# IDebugDataSpaces4::SearchVirtual method



## -description
The <b>SearchVirtual</b> method searches the target's virtual memory for a specified pattern of bytes.



## -syntax

````
HRESULT SearchVirtual(
  [in]  ULONG64  Offset,
  [in]  ULONG64  Length,
  [in]  PVOID    Pattern,
  [in]  ULONG    PatternSize,
  [in]  ULONG    PatternGranularity,
  [out] PULONG64 MatchOffset
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space to start searching for the pattern.


### -param Length [in]

Specifies how far to search for the pattern.  A successful match requires the entire pattern to be found before <i>Length</i> bytes have been examined.


### -param Pattern [in]

Specifies the pattern to search for.


### -param PatternSize [in]

Specifies the size in bytes of the pattern.  This must be a multiple of the granularity of the pattern.


### -param PatternGranularity [in]

Specifies the granularity of the pattern.  For a successful match the pattern must occur a multiple of this value after the start location.


### -param MatchOffset [out]

Receives the location in the target's virtual address space of the pattern, if it was found.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_MORE_ENTRIES)</b></dt>
</dl>After examining <i>Length</i> bytes the pattern was not found.

 


## -remarks
This method searches the target's virtual memory for the first occurrence, subject to granularity, of the pattern entirely contained in the <i>Length</i> bytes of the target's memory starting at the location <i>Offset</i>.

<i>PatternGranularity</i> can be used to ensure the alignment of the match relative to <i>Offset</i>.  For example, a value of 0x4 can be used to require alignment to a DWORD.  A value of 0x1 can be used to allow the pattern to start anywhere.

For additional options, including the ability to restrict the search to writable memory, see <a href="debugger.searchvirtual2">SearchVirtual2</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="debugger.readvirtual">ReadVirtual</a>
</dt>
<dt>
<a href="debugger.searchvirtual2">SearchVirtual2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugDataSpaces::SearchVirtual method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
