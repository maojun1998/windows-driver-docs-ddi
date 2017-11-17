---
UID: NF.wiautil.wiauDbgFlags
title: wiauDbgFlags
author: windows-driver-content
description: The wiauDbgFlags function determines whether a particular debugging flag is set.
old-location: image\wiaudbgflags.htm
ms.assetid: 2185a1c0-e952-4dbd-b1a9-82339e417774
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: image
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiauDbgFlags
req.alt-loc: Wiautil.h
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
ms.keywords: wiauDbgFlags
req.iface: 
req.product: Windows 10 or later.
---

# wiauDbgFlags function



## -description
<p>The <b>wiauDbgFlags</b> function determines whether a particular debugging flag is set.</p>


## -syntax

````
inline void __stdcall wiauDbgFlags(
   DWORD    flags,
   LPCSTR   prefix,
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````


## -parameters
<dl>

### -param <i>flags</i> 

<dd>
<p>Is a set of flags that control which information is placed in the log file or displayed in the debugger. See the <i>flags</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550159">wiauDbgSetFlags</a> for a list of the flag values.</p>
</dd>

### -param <i>prefix</i> 

<dd>
<p>Pointer to a string containing a prefix (such as "ERROR " or "WARN ").</p>
</dd>

### -param <i>fname</i> 

<dd>
<p>Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.</p>
</dd>

### -param <i>fmt, ...</i> 

<dd>
<p>Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If message logging to log file, or debugger, or both is enabled and the particular flag in the <i>flags</i> parameter is enabled, this function logs a message containing the strings pointed to by the <i>prefix</i>, <i>fname</i>, and <i>fmt</i> parameters.</p>

<p>If message logging to log file, or debugger, or both is enabled and the particular flag in the <i>flags</i> parameter is enabled, this function logs a message containing the strings pointed to by the <i>prefix</i>, <i>fname</i>, and <i>fmt</i> parameters.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows XP and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wiautil.h (include Wiautil.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550159">wiauDbgSetFlags</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgFlags function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>