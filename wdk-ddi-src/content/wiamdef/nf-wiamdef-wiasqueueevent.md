---
UID: NF.wiamdef.wiasQueueEvent
title: wiasQueueEvent
author: windows-driver-content
description: The wiasQueueEvent function informs the service that the device generated an event.
old-location: image\wiasqueueevent.htm
ms.assetid: 1ea82b64-e0e0-445b-8200-70cd6920d29b
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
req.alt-api: wiasQueueEvent
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
ms.keywords: wiasQueueEvent
req.iface: 
req.product: Windows 10 or later.
---

# wiasQueueEvent function



## -description
<p>The <b>wiasQueueEvent</b> function informs the service that the device generated an event. </p>


## -syntax

````
HRESULT _stdcall wiasQueueEvent(
  _In_           BSTR bstrDeviceId,
  _In_     const GUID *pEventGUID,
  _In_opt_       BSTR bstrFullItemName
);
````


## -parameters
<dl>

### -param <i>bstrDeviceId</i> [in]

<dd>
<p>Specifies the device ID. This is the value passed to the minidriver in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544986">IWiaMiniDrv::drvInitializeWia</a> method.</p>
</dd>

### -param <i>pEventGUID</i> [in]

<dd>
<p>Pointer to a buffer that contains the GUID for the event.</p>
</dd>

### -param <i>bstrFullItemName</i> [in, optional]

<dd>
<p>Specifies the full item name, including path information.</p>
</dd>
</dl>

## -returns
<p>On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).</p>

## -remarks
<p>This method should be used whenever the device must signal that an event of some type occurred. The device does this by placing the event on the event queue. For example, when a camera takes a new picture, it should generate a WIA_EVENT_ITEM_CREATED event after adding a new driver item to its tree. The camera can place this event on the event queue in this way:</p>

<p>See the Windows SDK documentation for a complete list of WIA event identifiers.</p>

<p>This method should be used whenever the device must signal that an event of some type occurred. The device does this by placing the event on the event queue. For example, when a camera takes a new picture, it should generate a WIA_EVENT_ITEM_CREATED event after adding a new driver item to its tree. The camera can place this event on the event queue in this way:</p>

<p>See the Windows SDK documentation for a complete list of WIA event identifiers.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544986">IWiaMiniDrv::drvInitializeWia</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasQueueEvent function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>