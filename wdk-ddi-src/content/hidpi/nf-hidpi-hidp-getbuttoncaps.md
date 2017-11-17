---
UID: NF.hidpi.HidP_GetButtonCaps
title: HidP_GetButtonCaps
author: windows-driver-content
description: The HidP_GetButtonCaps routine returns a button capability array that describes all the HID control buttons in a top-level collection for a specified type of HID report.
old-location: hid\hidp_getbuttoncaps.htm
ms.assetid: 228b95b0-1087-422f-a995-809743c6103e
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: hid
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HidP_GetButtonCaps
req.alt-loc: Hidparse.lib,Hidparse.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hidparse.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: HidP_GetButtonCaps
req.iface: 
---

# HidP_GetButtonCaps function



## -description
<p>The <b>HidP_GetButtonCaps</b> routine returns a <a href="https://msdn.microsoft.com/139324e5-4d46-4d00-9f5a-fd0313fc109a">button capability array</a> that describes all the HID control buttons in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> for a specified type of HID report.</p>


## -syntax

````
NTSTATUS __stdcall HidP_GetButtonCaps(
  _In_    HIDP_REPORT_TYPE     ReportType,
  _Out_   PHIDP_BUTTON_CAPS    ButtonCaps,
  _Inout_ PUSHORT              ButtonCapsLength,
  _In_    PHIDP_PREPARSED_DATA PreparsedData
);
````


## -parameters
<dl>

### -param <i>ReportType</i> [in]

<dd>
<p>Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.</p>
</dd>

### -param <i>ButtonCaps</i> [out]

<dd>
<p>Pointer to a caller-allocated buffer that the routine uses to return a button capability array for the specified report type.</p>
</dd>

### -param <i>ButtonCapsLength</i> [in, out]

<dd>
<p>Specifies the length on input, in array elements, of the buffer provided at <i>ButtonCaps</i>. On output, this parameter is set to the actual number of elements that the routine returns.</p>
</dd>

### -param <i>PreparsedData</i> [in]

<dd>
<p>Pointer to a top-level collection's <a href="NULL">preparsed data</a>.</p>
</dd>
</dl>

## -returns
<p><b>HidP_GetButtonCaps</b> returns one of the following status values:</p><dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl><p>The routine successfully returned the capability data.</p><dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl><p>The preparsed data is not valid.</p>

<p> </p>

## -remarks
<p><b>HidP_GetButtonCaps</b> returns the capability of all buttons in a top level collection for a specified report type. </p>

<p><i>ButtonCapsLength</i> should be set to the value of the <b>Number</b><i>Xxx</i><b>ButtonCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539697">HIDP_CAPS</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>, where <i>Xxx</i> specifies the report type.</p>

<p>To obtain a subset of button capabilities, selected by <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage</a>, <a href="hid.hid_usages#usage_page#usage_page">usage page</a>, or <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a>, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539733">HidP_GetSpecificButtonCaps</a>.</p>

<p>For more information about a collection's capability, see <a href="NULL">Obtaining Collection Information</a>.</p>

<p>See also <a href="NULL">HID Collections</a>. </p>

<p><b>HidP_GetButtonCaps</b> returns the capability of all buttons in a top level collection for a specified report type. </p>

<p><i>ButtonCapsLength</i> should be set to the value of the <b>Number</b><i>Xxx</i><b>ButtonCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539697">HIDP_CAPS</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>, where <i>Xxx</i> specifies the report type.</p>

<p>To obtain a subset of button capabilities, selected by <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage</a>, <a href="hid.hid_usages#usage_page#usage_page">usage page</a>, or <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a>, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539733">HidP_GetSpecificButtonCaps</a>.</p>

<p>For more information about a collection's capability, see <a href="NULL">Obtaining Collection Information</a>.</p>

<p>See also <a href="NULL">HID Collections</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hidpi.h (include Hidpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hidparse.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543586">_HIDP_PREPARSED_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539693">HIDP_BUTTON_CAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539733">HidP_GetSpecificButtonCaps</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_GetButtonCaps routine%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>