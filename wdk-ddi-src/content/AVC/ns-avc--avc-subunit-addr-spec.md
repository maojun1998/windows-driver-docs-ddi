---
UID: NS.avc._AVC_SUBUNIT_ADDR_SPEC
title: AVC_SUBUNIT_ADDR_SPEC
author: windows-driver-content
description: The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of avc.sys to describe virtual subunit addresses.
old-location: stream\avc_subunit_addr_spec.htm
ms.assetid: fa9fedc5-cacc-409a-99f5-7103b5424b3c
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVC_SUBUNIT_ADDR_SPEC
req.alt-loc: avc.h
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
ms.keywords: AVC_SUBUNIT_ADDR_SPEC, AVC_SUBUNIT_ADDR_SPEC, *PAVC_SUBUNIT_ADDR_SPEC
req.iface: 
---

# AVC_SUBUNIT_ADDR_SPEC structure



## -description
<p>The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of <i>avc.sys</i> to describe virtual subunit addresses.</p>


## -syntax

````
typedef struct _AVC_SUBUNIT_ADDR_SPEC {
  ULONG Flags;
  UCHAR SubunitAddress[1];
} AVC_SUBUNIT_ADDR_SPEC, *PAVC_SUBUNIT_ADDR_SPEC;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>The flags extend the operation in the following ways:</p>
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>AVC_SUBUNIT_ADDR_PERSISTENT</p>
</td>
<td>
<p>Makes the change persistent (in the registry) so on reboot the virtual device instances are automatically enumerated.</p>
</td>
</tr>
<tr>
<td>
<p>AVC_SUBUNIT_ADDR_TRIGGERBUSRESET</p>
</td>
<td>
<p>Informs Device Manager that the PDO list has changed. This causes a 1394 bus reset, which notifies devices on the 1394 bus that the topology has changed. This flag is normally set, unless there are several different subunit types to enable at the same time. The IOCTL_AVC_BUS_RESET control code performs the equivalent bus reset operation.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>SubunitAddress</b>

<dd>
<p>A Subunit Address encoded according to Section 5.3.3 of the AV/C Digital Interface Command Set General Specification, Rev 3.0. This specification can be found at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8728">1394 Trade Association</a> website. The ID part (<b>SubunitAddress</b>[0] &amp; 0x7) represents the max ID (not the count of subunits), so to enumerate a single tuner subunit, you would specify 0x28 (0x5 &lt;&lt; 3). This struct supports extended subunit addresses (just allocate a bigger struct and pass the actual length with the IOCTL).</p>
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
<dt>Avc.h (include Avc.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560783">IOCTL_AVC_BUS_RESET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_SUBUNIT_ADDR_SPEC structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>