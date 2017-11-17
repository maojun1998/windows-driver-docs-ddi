---
UID: NS.wiadevd.tagDEVICEDIALOGDATA
title: tagDEVICEDIALOGDATA
author: windows-driver-content
description: The DEVICEDIALOGDATA structure contains all the data needed to implement a custom device dialog.
old-location: image\devicedialogdata.htm
ms.assetid: 8ddd3ad7-fa97-45a4-a124-ceccdfb93f7f
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: image
req.header: wiadevd.h
req.include-header: Wiadevd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVICEDIALOGDATA
req.alt-loc: wiadevd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
ms.keywords: tagDEVICEDIALOGDATA, DEVICEDIALOGDATA, *LPDEVICEDIALOGDATA, *PDEVICEDIALOGDATA
req.iface: 
req.product: Windows 10 or later.
---

# tagDEVICEDIALOGDATA structure



## -description
<p>The DEVICEDIALOGDATA structure contains all the data needed to implement a custom device dialog.</p>


## -syntax

````
typedef struct tagDEVICEDIALOGDATA {
  DWORD    cbSize;
  HWND     hwndParent;
  IWiaItem *pIWiaItemRoot;
  DWORD    dwFlags;
  LONG     lIntent;
  LONG     lItemCount;
  IWiaItem **ppWiaItems;
} DEVICEDIALOGDATA, *LPDEVICEDIALOGDATA, *PDEVICEDIALOGDATA;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd>
<p>Specifies the size of this structure in bytes.</p>
</dd>

### -field <b>hwndParent</b>

<dd>
<p>Specifies the handle to the parent window of the dialog.</p>
</dd>

### -field <b>pIWiaItemRoot</b>

<dd>
<p>Points to an <b>IWiaItem</b> interface that represents the valid root item in the application item tree. For more information about this interface, see the Windows SDK documentation.</p>
</dd>

### -field <b>dwFlags</b>

<dd>
<p>Specifies the flags passed to <b>IWiaItem::DeviceDlg</b> and <b>IWiaDevMgr::GetImageDlg</b> by the calling program. These methods are described in the Windows SDK documentation. The possible values for this member are WIA_DEVICE_DIALOG_SINGLE_IMAGE and WIA_DEVICE_DIALOG_USE_COMMON_UI (defined in <i>Wiadef.h</i>).</p>
</dd>

### -field <b>lIntent</b>

<dd>
<p>Specifies the intents passed to <b>IWiaItem::DeviceDlg</b> and <b>IWiaDevMgr::GetImageDlg</b> by the calling program (see the Windows SDK documentation).</p>
</dd>

### -field <b>lItemCount</b>

<dd>
<p>Specifies the number of items in the array to which <b>ppIWiaItems</b> points.</p>
</dd>

### -field <b>ppWiaItems</b>

<dd>
<p>Array of IWiaItem interface pointers. Array must</p>
</dd>
</dl>

## -remarks
<p>The DEVICEDIALOGDATA structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545069">IWiaUIExtension::DeviceDialog</a> method.</p>

<p>The array specified in <i>ppIWiaItems</i> must be allocated using <b>CoTaskMemAlloc</b>. All interface pointers indicated in the array must be initialized using the <b>AddRef</b> COM method. See the Windows SDK documentation for descriptions of these functions.</p>

<p>The <b>IWiaPropertyStorage</b> interface is used to access information about the <b>IWiaItem</b> object's properties. Applications must query an item to obtain its <b>IWiaPropertyStorage</b> interface. See the Windows SDK documentation for descriptions of this interface.</p>

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
<dt>Wiadevd.h (include Wiadevd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545069">IWiaUIExtension::DeviceDialog</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20DEVICEDIALOGDATA structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>