---
UID: NF.extsfns.IDebugFailureAnalysis2.GetFailureCode
title: IDebugFailureAnalysis2::GetFailureCode
author: windows-driver-content
description: The GetFailureCode method gets the bug check code or exception code of a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_getfailurecode.htm
ms.assetid: E407482E-26DD-40C6-9405-DF5CA8996B91
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: extsfns.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugFailureAnalysis2.GetFailureCode
req.alt-loc: extsfns.h
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
ms.keywords: IDebugFailureAnalysis2, GetFailureCode, IDebugFailureAnalysis2::GetFailureCode
req.iface: IDebugFailureAnalysis2
---

# IDebugFailureAnalysis2::GetFailureCode method



## -description
<p>The <b>GetFailureCode</b> method gets the bug check code or exception code of a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object.</p>


## -syntax

````
ULONG GetFailureCode();
````


## -parameters


## -returns
<p>This method returns a <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check code</a> or an <a href="http://go.microsoft.com/fwlink/p?LinkID=282670">exception code</a>.</p>

<p>This method returns a <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check code</a> or an <a href="http://go.microsoft.com/fwlink/p?LinkID=282670">exception code</a>.</p>

<p>This method returns a <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check code</a> or an <a href="http://go.microsoft.com/fwlink/p?LinkID=282670">exception code</a>.</p>

## -remarks
<p>When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs in response to a code failure, the analysis engine creates a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object to store data that describes and categorizes the failure. If the failure being analyzed is a bug check, this method returns a bug check code. If the failure being analyzed is an exception, this method returns an exception code.</p>

<p>When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs in response to a code failure, the analysis engine creates a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object to store data that describes and categorizes the failure. If the failure being analyzed is a bug check, this method returns a bug check code. If the failure being analyzed is an exception, this method returns an exception code.</p>

<p>When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs in response to a code failure, the analysis engine creates a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object to store data that describes and categorizes the failure. If the failure being analyzed is a bug check, this method returns a bug check code. If the failure being analyzed is an exception, this method returns an exception code.</p>

<p>When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs in response to a code failure, the analysis engine creates a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object to store data that describes and categorizes the failure. If the failure being analyzed is a bug check, this method returns a bug check code. If the failure being analyzed is an exception, this method returns an exception code.</p>

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
<dt>Extsfns.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983415">GetFailureClass</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetFailureCode method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>