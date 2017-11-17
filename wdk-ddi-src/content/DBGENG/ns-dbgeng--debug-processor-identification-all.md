---
UID: NS.dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALL
title: DEBUG_PROCESSOR_IDENTIFICATION_ALL
author: windows-driver-content
description: This union contains relevant information for a processor the supported processors.
old-location: debugger\debug_processor_identification_all.htm
ms.assetid: 2C4C03BC-0D84-4151-B1A1-FE76F0355CD6
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_PROCESSOR_IDENTIFICATION_ALL
req.alt-loc: DbgEng.h
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
ms.keywords: DEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL, *PDEBUG_PROCESSOR_IDENTIFICATION_ALL
req.iface: IDebugSystemObjects4
---

# DEBUG_PROCESSOR_IDENTIFICATION_ALL structure



## -description
<p>This union contains relevant information for a processor the supported processors. </p>


## -syntax

````
typedef union _DEBUG_PROCESSOR_IDENTIFICATION_ALL {
  DEBUG_PROCESSOR_IDENTIFICATION_ALPHA Alpha;
  DEBUG_PROCESSOR_IDENTIFICATION_AMD64 Amd64;
  DEBUG_PROCESSOR_IDENTIFICATION_IA64  Ia64;
  DEBUG_PROCESSOR_IDENTIFICATION_X86   X86;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM   Arm;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM64 Arm64;
} DEBUG_PROCESSOR_IDENTIFICATION_ALL;
````


## -struct-fields
<dl>

### -field <b>Alpha</b>

<dd>
<p>An Alpha processor as a <a href="https://msdn.microsoft.com/AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a> struct.</p>
</dd>

### -field <b>Amd64</b>

<dd>
<p>An AMD64 processor as a <a href="https://msdn.microsoft.com/71E28D54-19D2-4A62-9A63-633186F67AD5">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a> stuct. </p>
</dd>

### -field <b>Ia64</b>

<dd>
<p>An Italium architecture processor as a <a href="https://msdn.microsoft.com/8827D989-EB59-4474-97D8-9CD9BF24FCC1">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a> stuct.</p>
</dd>

### -field <b>X86</b>

<dd>
<p>An x86 processor as a <a href="https://msdn.microsoft.com/B5AD9CE8-B0F0-49BC-984E-4372FD3BF93B">DEBUG_PROCESSOR_IDENTIFICATION_X86</a> struct.</p>
</dd>

### -field <b>Arm</b>

<dd>
<p>An ARM processor as a <a href="https://msdn.microsoft.com/4C7D5959-7900-4482-A45C-61D66541C276">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a> struct.</p>
</dd>

### -field <b>Arm64</b>

<dd>
<p>An ARM64 processor as a <a href="https://msdn.microsoft.com/4F47EC75-4D68-4202-9B29-8F6FB36528A5">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a> struct. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/71E28D54-19D2-4A62-9A63-633186F67AD5">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4C7D5959-7900-4482-A45C-61D66541C276">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4F47EC75-4D68-4202-9B29-8F6FB36528A5">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8827D989-EB59-4474-97D8-9CD9BF24FCC1">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/B5AD9CE8-B0F0-49BC-984E-4372FD3BF93B">DEBUG_PROCESSOR_IDENTIFICATION_X86</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_PROCESSOR_IDENTIFICATION_ALL union%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>