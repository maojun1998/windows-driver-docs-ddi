---
UID: NS.wiamindr_lh._WIA_PROPERTY_CONTEXT
title: WIA_PROPERTY_CONTEXT
author: windows-driver-content
description: The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context.
old-location: image\wia_property_context.htm
ms.assetid: afe92cb5-519a-46a3-a66d-c01b6a2c780b
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: image
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIA_PROPERTY_CONTEXT
req.alt-loc: wiamindr_lh.h
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
ms.keywords: WIA_PROPERTY_CONTEXT, WIA_PROPERTY_CONTEXT
req.iface: IWiaMiniDrvTransferCallback
req.product: Windows 10 or later.
---

# WIA_PROPERTY_CONTEXT structure



## -description
<p>The WIA_PROPERTY_CONTEXT structure stores property identifiers and their context. </p>


## -syntax

````
typedef struct _WIA_PROPERTY_CONTEXT {
  ULONG  cProps;
  PROPID *pProps;
  BOOL   *pChanged;
} WIA_PROPERTY_CONTEXT, *PWIA_PROPERTY_CONTEXT;
````


## -struct-fields
<dl>

### -field <b>cProps</b>

<dd>
<p>Specifies the number of property identifiers stored in this structure.</p>
</dd>

### -field <b>pProps</b>

<dd>
<p>Is an array of property identifiers that indicate the properties being written.</p>
</dd>

### -field <b>pChanged</b>

<dd>
<p>Is an array of Boolean values indicating which properties are changing. A member of this array is <b>TRUE</b> if the corresponding property is changing, and <b>FALSE</b> if the corresponding property is not changing. That is, if <b>pChanged</b>[n] is <b>TRUE</b>, <b>pProps</b>[n] will be changed, and if <b>pChanged</b>[n] is <b>FALSE</b>, <b>pProps</b>[n] will not be changed.</p>
</dd>
</dl>

## -remarks
<p>The Boolean values indicate whether the corresponding property is being written (changed) by an application calling <b>IPropertyStorage::WriteMultiple</b>, which is described in the Microsoft Windows SDK documentation.</p>

<p>Several WIA service library functions use the WIA_PROPERTY_CONTEXT structure. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff549167">wiasCreatePropContext</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549195">wiasFreePropContext</a> functions use it when a property context is created or freed. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff549271">wiasIsPropChanged</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549374">wiasSetPropChanged</a> use this structure to determine whether a property changed, and to modify a property context when the property does change. The <b>wiasGetChangedValue</b><i>Xxx</i> functions use this structure to determine whether a property of a certain type has changed. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff549448">wiasUpdateValidFormat</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549441">wiasUpdateScanRect</a> use it to, respectively, update a property context and to update the scanning area sizes for a scanning device.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Me and in Windows XP and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wiamindr_lh.h (include Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549167">wiasCreatePropContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549195">wiasFreePropContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549271">wiasIsPropChanged</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549374">wiasSetPropChanged</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549200">wiasGetChangedValueFloat</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549211">wiasGetChangedValueGuid</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549214">wiasGetChangedValueLong</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549219">wiasGetChangedValueStr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549448">wiasUpdateValidFormat</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549441">wiasUpdateScanRect</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIA_PROPERTY_CONTEXT structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>