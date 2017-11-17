---
UID: NF.wiamdef.wiasDebugTrace
title: wiasDebugTrace
author: windows-driver-content
description: This function prints a debug trace string in the Device Manager debug console.
old-location: image\wiasdebugtrace.htm
ms.assetid: db39c7f6-d966-4538-8ee9-d3623995535c
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: image
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiasDebugTrace
req.alt-loc: Wiaservc.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
ms.keywords: wiasDebugTrace
req.iface: 
req.product: Windows 10 or later.
---

# wiasDebugTrace function



## -description
<p>This function prints a debug trace string in the Device Manager debug console.</p>


## -syntax

````
VOID __cdecl wiasDebugTrace(
   HINSTANCE   hInstance,
   LPCSTR      pszFormat, ...
);
````


## -parameters
<dl>

### -param <i>hInstance</i> 

<dd>
<p>Is the module handle of calling module.</p>
</dd>

### -param <i>pszFormat, ...</i> 

<dd>
<p>Specifies a variable argument list, which starts with an ANSI format string containing the message and any format specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.</p>
</dd>
</dl>

## -returns
<p>On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).</p>

## -remarks
<p>The wiasDebugTrace function is not recommended for Windows XP and later. For Windows XP use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549600">WIAS_LTRACE</a> macro instead. For Windows Vista use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549619">WIAS_TRACE</a> macro instead.</p>

<p>To enable tracing in free builds, drivers must define the WIAS_DEBUG macro. Tracing is enabled by default in checked and debug builds of the operating system.</p>

<p>The wiasDebugTrace function is not recommended for Windows XP and later. For Windows XP use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549600">WIAS_LTRACE</a> macro instead. For Windows Vista use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549619">WIAS_TRACE</a> macro instead.</p>

<p>To enable tracing in free builds, drivers must define the WIAS_DEBUG macro. Tracing is enabled by default in checked and debug builds of the operating system.</p>

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
<p>Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wiamdef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wiaservc.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Wiaservc.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549600">WIAS_LTRACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549619">WIAS_TRACE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasDebugTrace function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>