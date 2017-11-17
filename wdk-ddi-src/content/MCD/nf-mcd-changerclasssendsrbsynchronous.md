---
UID: NF.mcd.ChangerClassSendSrbSynchronous
title: ChangerClassSendSrbSynchronous
author: windows-driver-content
description: The ChangerClassSendSrbSynchronous routine synchronously sends an SRB to a specified device.
old-location: storage\changerclasssendsrbsynchronous.htm
ms.assetid: 6765d7d5-528f-42c5-98c3-0484608a020b
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerClassSendSrbSynchronous
req.alt-loc: Mcd.lib,Mcd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mcd.lib
req.dll: 
req.irql: 
ms.keywords: ChangerClassSendSrbSynchronous
req.iface: 
---

# ChangerClassSendSrbSynchronous function



## -description
<p>The <b>ChangerClassSendSrbSynchronous</b> routine synchronously sends an SRB to a specified device.</p>


## -syntax

````
NTSTATUS ChangerClassSendSrbSynchronous(
  _In_ PDEVICE_OBJECT      DeviceObject,
  _In_ PSCSI_REQUEST_BLOCK Srb,
  _In_ PVOID               Buffer,
  _In_ ULONG               BufferSize,
  _In_ BOOLEAN             WriteToDevice
);
````


## -parameters
<dl>

### -param <i>DeviceObject</i> [in]

<dd>
<p>Pointer to the functional device object of the target device. </p>
</dd>

### -param <i>Srb</i> [in]

<dd>
<p>Pointer to a partially initialized SCSI request block (SRB) to be sent to the target device. </p>
</dd>

### -param <i>Buffer</i> [in]

<dd>
<p>Specifies address of the buffer that <i>Srb-&gt;</i><b>DataBuffer</b> should point to. <b>ChangerClassSendSrbSynchronous</b> creates an MDL for this buffer and passes it to the target device driver in the SRB IRP.</p>
</dd>

### -param <i>BufferSize</i> [in]

<dd>
<p>Specifies length, in bytes, of the buffer. </p>
</dd>

### -param <i>WriteToDevice</i> [in]

<dd>
<p>Indicates a write operation when <b>TRUE</b> and read operation when <b>FALSE</b>. </p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if the SRB is transmitted successfully or the appropriate error code if the SRB fails or cannot be sent for some reason. </p>

## -remarks
<p>Changer miniclass drivers can call this class driver routine in Microsoft Windows XP and later operating systems. Miniclass drivers should use this routine to send an SRB to the port driver instead of calling the <i>classpnp.sys</i> library routine <b>ClassSendSrbSynchronous</b> directly. Although <i>classpnp.sys </i>is shipped with the Windows Driver Kit (WDK), it is not a supported API, and drivers that call this library's routines directly might not function properly in future releases. </p>

<p><b>ChangerClassSendSrbSynchronous</b> finishes the initialization of the partially initialized SRB, setting the SRB's flags with the values indicated in the target's device object. <b>ChangerClassSendSrbSynchronous</b> creates the IRP that is used to convey the SRB to the target device, sends the IRP, then handles the IRP's completion. </p>

<p>If the IRP fails and the sense request data indicates that the IRP should be retried, <b>ChangerClassSendSrbSynchronous</b> will resend the IRP. </p>

<p>Changer miniclass drivers can call this class driver routine in Microsoft Windows XP and later operating systems. Miniclass drivers should use this routine to send an SRB to the port driver instead of calling the <i>classpnp.sys</i> library routine <b>ClassSendSrbSynchronous</b> directly. Although <i>classpnp.sys </i>is shipped with the Windows Driver Kit (WDK), it is not a supported API, and drivers that call this library's routines directly might not function properly in future releases. </p>

<p><b>ChangerClassSendSrbSynchronous</b> finishes the initialization of the partially initialized SRB, setting the SRB's flags with the values indicated in the target's device object. <b>ChangerClassSendSrbSynchronous</b> creates the IRP that is used to convey the SRB to the target device, sends the IRP, then handles the IRP's completion. </p>

<p>If the IRP fails and the sense request data indicates that the IRP should be retried, <b>ChangerClassSendSrbSynchronous</b> will resend the IRP. </p>

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
<dt>Mcd.h (include Mcd.h or Ntddchgr.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Mcd.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20ChangerClassSendSrbSynchronous routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>