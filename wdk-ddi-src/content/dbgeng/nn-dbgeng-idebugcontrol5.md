---
UID: NN:dbgeng.IDebugControl5
title: IDebugControl5
author: windows-driver-content
description: "."
old-location: debugger\idebugcontrol5.htm
old-project: debugger
ms.assetid: 6C358D49-970D-4687-B16E-7D1B44CB0A8E
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl5, IDebugControl5 interface [Windows Debugging], IDebugControl5 interface [Windows Debugging], described, dbgeng/IDebugControl5, debugger.idebugcontrol5
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl5
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl5 interface


## -description





## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl5</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>. <b>IDebugControl5</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugControl5</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818563">GetBreakpointByGuid</a>
</td>
<td align="left" width="63%">
The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818564">GetContextStackTraceEx</a>
</td>
<td align="left" width="63%">
The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818565">GetStackTraceEx</a>
</td>
<td align="left" width="63%">
The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818566">OutputContextStackTraceEx</a>
</td>
<td align="left" width="63%">
The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts. The OutputContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818567">OutputStackTraceEx</a>
</td>
<td align="left" width="63%">
The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

