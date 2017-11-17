---
UID: NF.winsplp.InitializePrintProvidor
title: InitializePrintProvidor
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\initializeprintprovidor.htm
ms.assetid: 54a5009d-9893-4766-b9fd-7e7474b55949
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: print
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: InitializePrintProvidor
req.alt-loc: winsplp.h
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
ms.keywords: InitializePrintProvidor
req.iface: 
req.product: Windows 10 or later.
---

# InitializePrintProvidor function



## -description

## -syntax

````
BOOL InitializePrintProvidor(
  _Out_    LPPRINTPROVIDOR pPrintProvidor,
  _In_     DWORD           cbPrintProvidor,
  _In_opt_ LPWSTR          pFullRegistryPath
);
````


## -parameters
<dl>

### -param <i>pPrintProvidor</i> [out]

<dd>
<p>Caller-supplied address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a> structure, to be filled in by the print provider.</p>
</dd>

### -param <i>cbPrintProvidor</i> [in]

<dd>
<p>Caller-supplied size, in bytes, of the PRINTPROVIDOR structure pointed to by <i>pPrintProvidor</i>.</p>
</dd>

### -param <i>pFullRegistryPath</i> [in, optional]

<dd>
<p>Caller-supplied pointer to a string representing the full registry path to the provider's registry entry.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function should return <b>TRUE</b>. Otherwise the function should return <b>FALSE</b>.</p>

## -remarks
<p>Print providers are required to define an <b>InitializePrintProvidor</b> function, which is the first function called by the spooler after the provider has been loaded. The function must fill the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a> structure with pointers to the provider's defined functions (see <a href="NULL">Functions Defined by Print Providers</a>). The function can also perform other provider-specific initialization operations.</p>

<p>Print providers are required to define an <b>InitializePrintProvidor</b> function, which is the first function called by the spooler after the provider has been loaded. The function must fill the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a> structure with pointers to the provider's defined functions (see <a href="NULL">Functions Defined by Print Providers</a>). The function can also perform other provider-specific initialization operations.</p>

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
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20InitializePrintProvidor function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>