---
UID: NF.video.VideoPortFreeDeviceBase
title: VideoPortFreeDeviceBase function
author: windows-driver-content
description: The VideoPortFreeDeviceBase function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling VideoPortGetDeviceBase.
old-location: display\videoportfreedevicebase.htm
old-project: display
ms.assetid: 5b165237-f6fb-449c-878d-0ee09076d203
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortFreeDeviceBase
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortFreeDeviceBase
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# VideoPortFreeDeviceBase function



## -description
The <b>VideoPortFreeDeviceBase</b> function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling <a href="display.videoportgetdevicebase">VideoPortGetDeviceBase</a>.


## -syntax

````
VOID VideoPortFreeDeviceBase(
   PVOID HwDeviceExtension,
   PVOID MappedAddress
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension.

### -param MappedAddress 

Specifies the base address of the mapped range to be freed. This value must be the same as the value returned by a preceding call to <b>VideoPortGetDeviceBase</b>.

## -returns
None

## -remarks
<b>VideoPortFreeDeviceBase</b> must be called from the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function if the miniport driver has already mapped an address range for an adapter it cannot support or does not use any longer.

When this occurs, the miniport driver also must release its claim on the corresponding hardware resources in the registry. To release all claims on resources for a particular adapter, call <a href="display.videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> or <a href="display.videoportgetaccessranges">VideoPortGetAccessRanges</a> with the <i>NumAccessRanges</i> parameter set to zero. To release claims on selected access ranges, do the following:

Modify the access ranges array of claimed bus-relative ranges for the adapter by setting the appropriate elements' <b>RangeLength</b>(s) to zero. Leave the current specification as is in all elements on which the miniport driver will not release its claims.

Call <a href="display.videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> with this modified <i>AccessRanges</i> array.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>
</dt>
<dt>
<a href="display.videoportgetaccessranges">VideoPortGetAccessRanges</a>
</dt>
<dt>
<a href="display.videoportgetdevicebase">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="display.videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortFreeDeviceBase function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>