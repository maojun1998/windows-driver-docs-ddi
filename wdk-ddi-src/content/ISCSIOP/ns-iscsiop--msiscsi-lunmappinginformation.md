---
UID: NS.iscsiop._MSiSCSI_LUNMappingInformation
title: MSiSCSI_LUNMappingInformation
author: windows-driver-content
description: This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit.
old-location: storage\msiscsi_lunmappinginformation.htm
ms.assetid: abe4b0fe-3918-4139-9c35-d9399287ce03
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSiSCSI_LUNMappingInformation
req.alt-loc: iscsiop.h
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
ms.keywords: MSiSCSI_LUNMappingInformation, MSiSCSI_LUNMappingInformation, *PMSiSCSI_LUNMappingInformation
req.iface: 
---

# MSiSCSI_LUNMappingInformation structure



## -description
<p>This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit.</p>


## -syntax

````
typedef struct _MSiSCSI_LUNMappingInformation {
  ULONGLONG UniqueAdapterId;
  ULONGLONG UniqueSessionId;
  ULONG     OSBus;
  ULONG     OSTarget;
  ULONG     OSLUN;
} MSiSCSI_LUNMappingInformation, *PMSiSCSI_LUNMappingInformation;
````


## -struct-fields
<dl>

### -field <b>UniqueAdapterId</b>

<dd>
<p>A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure.</p>
</dd>

### -field <b>UniqueSessionId</b>

<dd>
<p>A session ID that uniquely identifies the session for which the LUN mapping is valid. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.</p>
</dd>

### -field <b>OSBus</b>

<dd>
<p>The number that the operating system assigns to the bus that the adapter is attached to.</p>
</dd>

### -field <b>OSTarget</b>

<dd>
<p>The device number that the operating system assigns to the target.</p>
</dd>

### -field <b>OSLUN</b>

<dd>
<p>The logical unit number (LUN) that the operating system assigns to the logical unit.</p>
</dd>
</dl>

## -remarks
<p>You must implement this class.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563067">MSiSCSI_LUNMappingInformation WMI Class</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563144">MSiSCSI_TargetMappings</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20MSiSCSI_LUNMappingInformation structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>