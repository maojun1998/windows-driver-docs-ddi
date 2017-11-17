---
UID: NS.usbioctl._USB_NODE_CONNECTION_DRIVERKEY_NAME
title: USB_NODE_CONNECTION_DRIVERKEY_NAME
author: windows-driver-content
description: The USB_NODE_CONNECTION_DRIVERKEY_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME I/O control request to retrieve the driver key name for the device that is connected to the indicated port.
old-location: buses\usb_node_connection_driverkey_name.htm
ms.assetid: b5939a5b-2856-494c-9673-d32e2fc93384
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: usbref
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_NODE_CONNECTION_DRIVERKEY_NAME
req.alt-loc: usbioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: USB_NODE_CONNECTION_DRIVERKEY_NAME, USB_NODE_CONNECTION_DRIVERKEY_NAME, *PUSB_NODE_CONNECTION_DRIVERKEY_NAME
req.iface: 
req.product: Windows 10 or later.
---

# USB_NODE_CONNECTION_DRIVERKEY_NAME structure



## -description
<p>The <b>USB_NODE_CONNECTION_DRIVERKEY_NAME</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537317">IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME</a> I/O control request to retrieve the driver key name for the device that is connected to the indicated port.</p>


## -syntax

````
typedef struct _USB_NODE_CONNECTION_DRIVERKEY_NAME {
  ULONG ConnectionIndex;
  ULONG ActualLength;
  WCHAR DriverKeyName[1];
} USB_NODE_CONNECTION_DRIVERKEY_NAME, *PUSB_NODE_CONNECTION_DRIVERKEY_NAME;
````


## -struct-fields
<dl>

### -field <b>ConnectionIndex</b>

<dd>
<p>On input, the port number that the device is connected to.</p>
</dd>

### -field <b>ActualLength</b>

<dd>
<p>On output, the length, in bytes, of the string in <b>DriverKeyName</b>.</p>
</dd>

### -field <b>DriverKeyName</b>

<dd>
<p>On output, the driver key name for the device that is attached to the port that is indicated by <b>ConnectionIndex</b>. This name is represented as a Unicode string.</p>
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
<dt>Usbioctl.h (include Usbioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537317">IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_NODE_CONNECTION_DRIVERKEY_NAME structure%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>