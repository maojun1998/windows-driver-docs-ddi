---
UID: NE.usb._USBD_PIPE_TYPE
title: USBD_PIPE_TYPE
author: windows-driver-content
description: The USBD_PIPE_TYPE enumerator indicates the type of pipe.
old-location: buses\usbd_pipe_type.htm
ms.assetid: 4522a7d0-d297-4668-bb4e-e4ceae18f52a
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: usbref
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_PIPE_TYPE
req.alt-loc: usb.h
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
ms.keywords: URS_CONFIG, URS_CONFIG, *PURS_CONFIG
req.iface: 
req.product: Windows 10 or later.
---

# USBD_PIPE_TYPE enumeration



## -description
<p>The <b>USBD_PIPE_TYPE</b> enumerator indicates the type of pipe.</p>


## -syntax

````
typedef enum _USBD_PIPE_TYPE { 
  UsbdPipeTypeControl      = 0,
  UsbdPipeTypeIsochronous  = 1,
  UsbdPipeTypeBulk         = 2,
  UsbdPipeTypeInterrupt    = 3
} USBD_PIPE_TYPE;
````


## -enum-fields
<dl>

### -field <a id="UsbdPipeTypeControl"></a><a id="usbdpipetypecontrol"></a><a id="USBDPIPETYPECONTROL"></a><b>UsbdPipeTypeControl</b>

<dd>
<p>Indicates that the pipe is a control pipe. </p>
</dd>

### -field <a id="UsbdPipeTypeIsochronous"></a><a id="usbdpipetypeisochronous"></a><a id="USBDPIPETYPEISOCHRONOUS"></a><b>UsbdPipeTypeIsochronous</b>

<dd>
<p>Indicates that the pipe is an isochronous transfer pipe.</p>
</dd>

### -field <a id="UsbdPipeTypeBulk"></a><a id="usbdpipetypebulk"></a><a id="USBDPIPETYPEBULK"></a><b>UsbdPipeTypeBulk</b>

<dd>
<p>Indicates that the pipe is a bulk transfer pipe. </p>
</dd>

### -field <a id="UsbdPipeTypeInterrupt"></a><a id="usbdpipetypeinterrupt"></a><a id="USBDPIPETYPEINTERRUPT"></a><b>UsbdPipeTypeInterrupt</b>

<dd>
<p>Indicates that the pipe is a interrupt pipe. </p>
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
<dt>Usb.h (include Usb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_PIPE_TYPE enumeration%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>