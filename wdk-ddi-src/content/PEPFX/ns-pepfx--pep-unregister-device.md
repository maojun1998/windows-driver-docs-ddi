---
UID: NS.pepfx._PEP_UNREGISTER_DEVICE
title: PEP_UNREGISTER_DEVICE
author: windows-driver-content
description: The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx).
old-location: kernel\pep_unregister_device.htm
ms.assetid: B6A0F80C-8AE2-4FFE-A3EE-F0260A8774D6
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_UNREGISTER_DEVICE
req.alt-loc: pepfx.h
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
ms.keywords: PEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE, *PPEP_UNREGISTER_DEVICE
req.iface: 
---

# PEP_UNREGISTER_DEVICE structure



## -description
<p>The <b>PEP_UNREGISTER_DEVICE</b> structure identifies a device whose registration is being removed from the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx).</p>


## -syntax

````
typedef struct _PEP_UNREGISTER_DEVICE {
  PEPHANDLE DeviceHandle;
} PEP_UNREGISTER_DEVICE, *PPEP_UNREGISTER_DEVICE;
````


## -struct-fields
<dl>

### -field <b>DeviceHandle</b>

<dd>
<p>[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_dpm_unregister_device">PEP_DPM_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="kernel.pep_dpm_unregister_device">PEP_DPM_UNREGISTER_DEVICE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_UNREGISTER_DEVICE structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>