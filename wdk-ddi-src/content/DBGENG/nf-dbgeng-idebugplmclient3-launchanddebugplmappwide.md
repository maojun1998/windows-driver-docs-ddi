---
UID: NF.dbgeng.IDebugPlmClient3.LaunchAndDebugPlmAppWide
title: IDebugPlmClient3::LaunchAndDebugPlmAppWide
author: windows-driver-content
description: Launches and attaches to a Process Lifecycle Management (PLM) application.
old-location: debugger\idebugplmclient3_launchanddebugplmappwide.htm
ms.assetid: F3DD5912-46E5-43E5-A920-940FC8FCD83F
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
req.alt-api: IDebugPlmClient3.LaunchAndDebugPlmAppWide
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
ms.keywords: IDebugPlmClient3, LaunchAndDebugPlmAppWide, IDebugPlmClient3::LaunchAndDebugPlmAppWide
req.iface: IDebugPlmClient3
---

# IDebugPlmClient3::LaunchAndDebugPlmAppWide method



## -description
<p>    Launches and attaches to a Process Lifecycle Management (PLM) application. </p>


## -syntax

````
HRESULT LaunchAndDebugPlmAppWide(
  [in] ULONG64 Server,
  [in] PCWSTR  PackageFullName,
  [in] PCWSTR  AppName,
  [in] PCWSTR  Arguments
);
````


## -parameters
<dl>

### -param <i>Server</i> [in]

<dd>
<p>The server of the application.</p>
</dd>

### -param <i>PackageFullName</i> [in]

<dd>
<p>A pointer to the package name.</p>
</dd>

### -param <i>AppName</i> [in]

<dd>
<p>A pointer to the application name. </p>
</dd>

### -param <i>Arguments</i> [in]

<dd>
<p>A pointer to an arguments string. </p>
</dd>
</dl>

## -returns
<p>If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.</p>

<p>If a debugger session is not already started, this method starts one. </p>

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
<a href="https://msdn.microsoft.com/5B0580FF-0829-406A-B511-C0CD91A08D5F">IDebugPlmClient3</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugPlmClient3::LaunchAndDebugPlmAppWide method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>