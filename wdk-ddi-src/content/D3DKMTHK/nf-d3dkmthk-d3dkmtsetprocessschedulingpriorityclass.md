---
UID: NF.d3dkmthk.D3DKMTSetProcessSchedulingPriorityClass
title: D3DKMTSetProcessSchedulingPriorityClass
author: windows-driver-content
description: The D3DKMTSetProcessSchedulingPriorityClass function sets the scheduling priority for a process.
old-location: display\d3dkmtsetprocessschedulingpriorityclass.htm
ms.assetid: 1c0177da-5e5f-4e3e-aef2-05d8079bfb95
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTSetProcessSchedulingPriorityClass
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
ms.keywords: D3DKMTSetProcessSchedulingPriorityClass
req.iface: 
---

# D3DKMTSetProcessSchedulingPriorityClass function



## -description
<p>The <b>D3DKMTSetProcessSchedulingPriorityClass</b> function sets the scheduling priority for a process.</p>


## -syntax

````
NTSTATUS APIENTRY D3DKMTSetProcessSchedulingPriorityClass(
  _In_ HANDLE                         hProcess,
  _In_ D3DKMT_SCHEDULINGPRIORITYCLASS Priority
);
````


## -parameters
<dl>

### -param <i>hProcess</i> [in]

<dd>
<p>A handle to the process that scheduling priority is set for.</p>
</dd>

### -param <i>Priority</i> [in]

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff548248">D3DKMT_SCHEDULINGPRIORITYCLASS</a>-typed value that indicates the priority level to set for the process.</p>
</dd>
</dl>

## -returns
<p><b>D3DKMTSetProcessSchedulingPriorityClass</b> returns one of the following values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The scheduling priority was successfully set.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>Parameters were validated and determined to be incorrect.</p>

<p> </p>

<p>This function might also return other NTSTATUS values.</p>

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
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Gdi32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Gdi32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548248">D3DKMT_SCHEDULINGPRIORITYCLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546992">D3DKMTGetProcessSchedulingPriorityClass</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetProcessSchedulingPriorityClass function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>