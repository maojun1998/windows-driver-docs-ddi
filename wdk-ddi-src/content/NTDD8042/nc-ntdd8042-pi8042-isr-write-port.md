---
UID: NC.ntdd8042.PI8042_ISR_WRITE_PORT
title: PI8042_ISR_WRITE_PORT
author: windows-driver-content
description: The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback.
old-location: hid\pi8042_isr_write_port.htm
ms.assetid: deded3fb-f0b3-4af5-b8b4-03658293b0fc
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: hid
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: I8042IsrWritePort
req.alt-loc: ntdd8042.h
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
ms.keywords: MSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes
req.iface: 
---

# PI8042_ISR_WRITE_PORT callback



## -description
<p>The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback.</p>


## -prototype

````
PI8042_ISR_WRITE_PORT I8042IsrWritePort;

VOID I8042IsrWritePort(
  _In_ PVOID Context,
  _In_ UCHAR Value
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>Pointer to the function device object that represents a keyboard or mouse device.</p>
</dd>

### -param <i>Value</i> [in]

<dd>
<p>Specifies the data to write to an i8042 port.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The PI8042_ISR_WRITE_PORT callback should only be called by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a> callback or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543252">PI8042_MOUSE_ISR</a> callback. I8042prt calls a vendor-supplied ISR callback for a device in the corresponding I8042prt device ISR.</p>

<p>I8042prt specifies the keyboard write port callback in the <b>IsrWritePort</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541039">INTERNAL_I8042_HOOK_KEYBOARD</a> structure that I8042prt uses with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.</p>

<p>I8042prt specifies the mouse write port callback in the <b>IsrWritePort</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541044">INTERNAL_I8042_HOOK_MOUSE</a> structure that I8042prt uses with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.</p>

<p>The PI8042_ISR_WRITE_PORT callback runs in kernel mode at the same IRQL as the I8042prt ISR for the device.</p>

<p>The PI8042_ISR_WRITE_PORT callback should only be called by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a> callback or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543252">PI8042_MOUSE_ISR</a> callback. I8042prt calls a vendor-supplied ISR callback for a device in the corresponding I8042prt device ISR.</p>

<p>I8042prt specifies the keyboard write port callback in the <b>IsrWritePort</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541039">INTERNAL_I8042_HOOK_KEYBOARD</a> structure that I8042prt uses with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.</p>

<p>I8042prt specifies the mouse write port callback in the <b>IsrWritePort</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541044">INTERNAL_I8042_HOOK_MOUSE</a> structure that I8042prt uses with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.</p>

<p>The PI8042_ISR_WRITE_PORT callback runs in kernel mode at the same IRQL as the I8042prt ISR for the device.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntdd8042.h (include Ntdd8042.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541044">INTERNAL_I8042_HOOK_MOUSE</a>
</dt>
<dt><b>IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541242">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PI8042_ISR_WRITE_PORT callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>