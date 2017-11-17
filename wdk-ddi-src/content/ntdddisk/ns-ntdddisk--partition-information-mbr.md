---
UID: NS.ntdddisk._PARTITION_INFORMATION_MBR
title: PARTITION_INFORMATION_MBR
author: windows-driver-content
description: PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.
old-location: storage\partition_information_mbr.htm
ms.assetid: 846f3a1c-ee0a-42d2-bdf1-7bf09406c955
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntdddisk.h
req.include-header: Ntddk.h, Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PARTITION_INFORMATION_MBR
req.alt-loc: ntdddisk.h
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
ms.keywords: PARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR
req.iface: 
---

# PARTITION_INFORMATION_MBR structure



## -description
<p>PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.</p>


## -syntax

````
typedef struct _PARTITION_INFORMATION_MBR {
  UCHAR   PartitionType;
  BOOLEAN BootIndicator;
  BOOLEAN RecognizedPartition;
  ULONG   HiddenSectors;
} PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR;
````


## -struct-fields
<dl>

### -field <b>PartitionType</b>

<dd>
<p>Specifies the partition type. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> for a list of system-defined partition types.</p>
</dd>

### -field <b>BootIndicator</b>

<dd>
<p>Indicates, when <b>TRUE</b>, that the partition is bootable. When <b>FALSE</b>, the partition is not bootable.</p>
</dd>

### -field <b>RecognizedPartition</b>

<dd>
<p>Indicates, when <b>TRUE</b>, that this is a partition with a recognized partition type. When <b>FALSE</b> this is a not a partition with a recognized partition.</p>
</dd>

### -field <b>HiddenSectors</b>

<dd>
<p>Contains the number of hidden sectors in the partition.</p>
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
<dt>Ntdddisk.h (include Ntddk.h or Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563763">PARTITION_INFORMATION_GPT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20PARTITION_INFORMATION_MBR structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>