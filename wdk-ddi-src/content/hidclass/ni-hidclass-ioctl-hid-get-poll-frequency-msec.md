---
UID: NI.hidclass.IOCTL_HID_GET_POLL_FREQUENCY_MSEC
title: IOCTL_HID_GET_POLL_FREQUENCY_MSEC
author: windows-driver-content
description: The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a top-level collection.
old-location: hid\ioctl_hid_get_poll_frequency_msec.htm
ms.assetid: 602dc6ac-89cc-4feb-9cef-5226c8abb085
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: hid
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_GET_POLL_FREQUENCY_MSEC
req.alt-loc: hidclass.h
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
ms.keywords: HDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
req.iface: 
---

# IOCTL_HID_GET_POLL_FREQUENCY_MSEC IOCTL



## -description
<p>The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.</p>
<p>For general information about HIDClass devices, see <a href="NULL">HID Collections</a>. </p>


## -ioctlparameters

### -input-buffer
<p><b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(ULONG). </p>

### -input-buffer-length
<p>Greater than or equal to <b>sizeof</b>(ULONG). </p>

<p>Greater than or equal to <b>sizeof</b>(ULONG). </p>

### -output-buffer
<p><b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the polling frequency. </p>

<p><b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the polling frequency. </p>

<p><b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the polling frequency. </p>

### -output-buffer-length
<p></p>

<p></p>

<p></p>

<p></p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. </p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. </p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. </p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. </p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. </p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hidclass.h (include Hidclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541216">IOCTL_HID_SET_POLL_FREQUENCY_MSEC</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_POLL_FREQUENCY_MSEC control code%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>