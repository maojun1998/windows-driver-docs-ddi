---
UID: NF.wiamdef.wiasSetValidListLong
title: wiasSetValidListLong
author: windows-driver-content
description: The wiasSetValidListLong function sets the valid values for a WIA_PROP_LIST property of type VT_I4.
old-location: image\wiassetvalidlistlong.htm
ms.assetid: a8c3d2fa-7c21-4c6a-b395-af28029c9c15
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
req.alt-api: wiasSetValidListLong
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
ms.keywords: wiasSetValidListLong
req.iface: 
req.product: Windows 10 or later.
---

# wiasSetValidListLong function



## -description
<p>The <b>wiasSetValidListLong </b>function sets the valid values for a WIA_PROP_LIST property of type VT_I4.</p>


## -syntax

````
HRESULT _stdcall wiasSetValidListLong(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       ULONG  ulCount,
       LONG   lNom,
       LONG   *plValues
);
````


## -parameters
<dl>

### -param <i>pWiasContext</i> [in]

<dd>
<p>Pointer to a WIA item context.</p>
</dd>

### -param <i>propid</i> 

<dd>
<p>Specifies the identifier of the property to be updated.</p>
</dd>

### -param <i>ulCount</i> 

<dd>
<p>Specifies the number of items in the <i>plValues</i> array.</p>
</dd>

### -param <i>lNom</i> 

<dd>
<p>Specifies the property's nominal value.</p>
</dd>

### -param <i>plValues</i> 

<dd>
<p>Pointer to the first element of an array of valid property values.</p>
</dd>
</dl>

## -returns
<p>On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).</p>

## -remarks


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549399">wiasSetValidListFloat</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549409">wiasSetValidListGuid</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549421">wiasSetValidListStr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549390">wiasSetValidFlag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549425">wiasSetValidRangeFloat</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549434">wiasSetValidRangeLong</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidListLong function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>