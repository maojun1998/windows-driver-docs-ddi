---
UID: NS.ntdd8042._INTERNAL_I8042_HOOK_KEYBOARD
title: INTERNAL_I8042_HOOK_KEYBOARD
author: windows-driver-content
description: INTERNAL_I8042_HOOK_KEYBOARD is used by I8042prt to connect optional callback routines that supplement keyboard initialization and the keyboard ISR. The callbacks can be supplied by an optional, vendor-supplied, upper-level filter driver.
old-location: hid\internal_i8042_hook_keyboard.htm
ms.assetid: 7a70f6e1-cf3b-4158-97f2-39f62a1d51ae
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: hid
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: INTERNAL_I8042_HOOK_KEYBOARD
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
req.irql: 
ms.keywords: INTERNAL_I8042_HOOK_KEYBOARD, INTERNAL_I8042_HOOK_KEYBOARD, *PINTERNAL_I8042_HOOK_KEYBOARD
req.iface: 
---

# INTERNAL_I8042_HOOK_KEYBOARD structure



## -description
<p>INTERNAL_I8042_HOOK_KEYBOARD is used by I8042prt to connect optional callback routines that supplement keyboard initialization and the keyboard ISR. The callbacks can be supplied by an optional, vendor-supplied, upper-level filter driver.</p>


## -syntax

````
typedef struct _INTERNAL_I8042_HOOK_KEYBOARD {
  PVOID                                  Context;
  PI8042_KEYBOARD_INITIALIZATION_ROUTINE InitializationRoutine;
  PI8042_KEYBOARD_ISR                    IsrRoutine;
  PI8042_ISR_WRITE_PORT                  IsrWritePort;
  PI8042_QUEUE_PACKET                    QueueKeyboardPacket;
  PVOID                                  CallContext;
} INTERNAL_I8042_HOOK_KEYBOARD, *PINTERNAL_I8042_HOOK_KEYBOARD;
````


## -struct-fields
<dl>

### -field <b>Context</b>

<dd>
<p>Pointer, if non-<b>NULL</b>, to the context that must be used with the <b>InitializationRoutine</b> and <b>IsrRoutine</b> routines. Otherwise, <b>Context</b> is <b>NULL</b>. </p>
</dd>

### -field <b>InitializationRoutine</b>

<dd>
<p>Pointer, if non-<b>NULL</b>, to an optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff543243">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>callback. I8042prt uses this callback to initialize a device after the device is reset. Otherwise, <b>IntializatonRoutine</b> is <b>NULL</b>.</p>
</dd>

### -field <b>IsrRoutine</b>

<dd>
<p>Pointer, if non-<b>NULL</b>, to an optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a> callback that customizes the operation of the I8042prt keyboard ISR. Otherwise, <b>IsrRoutine </b>is <b>NULL</b>.</p>
</dd>

### -field <b>IsrWritePort</b>

<dd>
<p>Pointer to the system-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543231">PI8042_ISR_WRITE_PORT</a> callback, which writes data to a keyboard.</p>
</dd>

### -field <b>QueueKeyboardPacket</b>

<dd>
<p>Pointer to the system-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543263">PI8042_QUEUE_PACKET</a> callback, which queues a keyboard input data packet for processing by the keyboard's ISR deferred procedure call.</p>
</dd>

### -field <b>CallContext</b>

<dd>
<p>Pointer to the context that must be used with the <b>IsrWritePort</b> and <b>QueueKeyboardPacket</b> routines. </p>
</dd>
</dl>

## -remarks
<p>This structure is only used with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request. </p>

<p><b>Context</b>, <b>InitializationRoutine</b>, and <b>IsrRoutine</b> can be supplied by an optional, vendor-supplied, upper-level filter driver.</p>

<p><b>IsrWritePort</b>, <b>QueueKeyboardPacket</b>, and <b>CallContext</b> are supplied by I8042prt.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541238">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1ea0ce84-f3e3-48af-8015-66fc35c17129">KbFilter_InitializationRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/0feca7de-aa80-4d1e-a5fc-901c18169649">KbFilter_IsrHook</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543231">PI8042_ISR_WRITE_PORT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543248">PI8042_KEYBOARD_ISR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543263">PI8042_QUEUE_PACKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20INTERNAL_I8042_HOOK_KEYBOARD structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>