---
UID: NC.dispmprt.DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION
title: DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION
author: windows-driver-content
description: Retrieves the current level of backlight reduction that is applied to the integrated display panel.
old-location: display\dxgkddigetbacklightreduction.htm
ms.assetid: 018cb4a0-e71d-407e-8fe9-716312099b73
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiGetBacklightReduction
req.alt-loc: Dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
req.iface: IDebugSystemObjects4
---

# DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback



## -description
<p>Retrieves the current level of backlight reduction that is applied to the integrated display panel.</p>


## -prototype

````
DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION DxgkDdiGetBacklightReduction;

NTSTATUS* DxgkDdiGetBacklightReduction(
  _In_  PVOID               Context,
  _Out_ DXGK_BACKLIGHT_INFO *BacklightInfo
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>A handle to a <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> context block that is associated with a display adapter. The display miniport driver's  function previously provided this handle to the DirectX graphics kernel subsystem.</p>
</dd>

### -param <i>BacklightInfo</i> [out]

<dd>
<p>A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/jj128357">DXGK_BACKLIGHT_INFO</a> that provides the current absolute level of backlight reduction.</p>
</dd>
</dl>

## -returns
<p>Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.</p>

## -remarks
<p>This function is mostly used for debugging and testing purposes to ensure a quality user experience with the display panel. The display miniport driver must always provide accurate information about the integrated display panel when this function is called.</p>

<p>Note that for some hardware a value of zero for <i>BacklightInfo</i>-&gt;<b>BacklightUsersetting</b> or <i>BacklightInfo</i>-&gt;<b>BacklightEffective</b> might not correspond to a Windows brightness level of zero percent. The operating system therefore requires absolute brightness information given by <b>BacklightUsersetting</b> and <b>BacklightEffective</b>. If the hardware uses brightness levels of 0 to 255, it must multiply those values by 256 to correctly map them to the 0 to 65535 range of <b>BacklightUsersetting</b> and <b>BacklightEffective</b>.</p>

<p>This function should be made pageable.</p>

<p>The backlight reduction ratio (<i>BRR</i>) is calculated as (<b>BacklightUsersetting</b> - <b>BacklightEffective</b>) / <b>BacklightUsersetting</b>.</p>

<p>The operating system assumes that, in response to a new brightness level request, the driver will boost pixel brightness by a factor of <b>BacklightUsersetting</b> / <b>BacklightEffective</b> = 1.0 / (1.0 - <i>BRR</i>).</p>

<p>As an example, if <i>BRR</i> = 0.2, the driver will typically boost brightness by a factor of 1.0 / (1.0 - <i>BRR</i>) = 1.25, so any pixel with a brightness value above 255 * (1.0 - <i>BRR</i>) = 204 will saturate. Using the value of <i>BacklightInfo</i>-&gt;<b>GammaRamp</b> provided by the driver, the operating system can more accurately estimate the distortion of pixel brightness for a particular image.</p>

<p>This function is mostly used for debugging and testing purposes to ensure a quality user experience with the display panel. The display miniport driver must always provide accurate information about the integrated display panel when this function is called.</p>

<p>Note that for some hardware a value of zero for <i>BacklightInfo</i>-&gt;<b>BacklightUsersetting</b> or <i>BacklightInfo</i>-&gt;<b>BacklightEffective</b> might not correspond to a Windows brightness level of zero percent. The operating system therefore requires absolute brightness information given by <b>BacklightUsersetting</b> and <b>BacklightEffective</b>. If the hardware uses brightness levels of 0 to 255, it must multiply those values by 256 to correctly map them to the 0 to 65535 range of <b>BacklightUsersetting</b> and <b>BacklightEffective</b>.</p>

<p>This function should be made pageable.</p>

<p>The backlight reduction ratio (<i>BRR</i>) is calculated as (<b>BacklightUsersetting</b> - <b>BacklightEffective</b>) / <b>BacklightUsersetting</b>.</p>

<p>The operating system assumes that, in response to a new brightness level request, the driver will boost pixel brightness by a factor of <b>BacklightUsersetting</b> / <b>BacklightEffective</b> = 1.0 / (1.0 - <i>BRR</i>).</p>

<p>As an example, if <i>BRR</i> = 0.2, the driver will typically boost brightness by a factor of 1.0 / (1.0 - <i>BRR</i>) = 1.25, so any pixel with a brightness value above 255 * (1.0 - <i>BRR</i>) = 204 will saturate. Using the value of <i>BacklightInfo</i>-&gt;<b>GammaRamp</b> provided by the driver, the operating system can more accurately estimate the distortion of pixel brightness for a particular image.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
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
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj128357">DXGK_BACKLIGHT_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>