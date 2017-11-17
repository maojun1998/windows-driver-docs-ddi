---
UID: NS.ntddstor._STORAGE_DEVICE_NUMBER
title: STORAGE_DEVICE_NUMBER
author: windows-driver-content
description: The STORAGE_DEVICE_NUMBER structure is used in conjunction with the IOCTL_STORAGE_GET_DEVICE_NUMBER request to retrieve the FILE_DEVICE_XXX device type, the device number, and, for a device that can be partitioned, the partition number assigned to a device by the driver when the device is started.
old-location: storage\storage_device_number.htm
ms.assetid: 3efed879-bde4-44ea-9af5-fc35a2ac27fc
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DEVICE_NUMBER
req.alt-loc: ntddstor.h
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
ms.keywords: STORAGE_DEVICE_NUMBER, STORAGE_DEVICE_NUMBER, *PSTORAGE_DEVICE_NUMBER
req.iface: 
---

# STORAGE_DEVICE_NUMBER structure



## -description
<p>The STORAGE_DEVICE_NUMBER structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560551">IOCTL_STORAGE_GET_DEVICE_NUMBER</a> request to retrieve the FILE_DEVICE_<i>XXX</i> device type, the device number, and, for a device that can be partitioned, the partition number assigned to a device by the driver when the device is started. </p>


## -syntax

````
typedef struct _STORAGE_DEVICE_NUMBER {
  DEVICE_TYPE DeviceType;
  ULONG       DeviceNumber;
  ULONG       PartitionNumber;
} STORAGE_DEVICE_NUMBER, *PSTORAGE_DEVICE_NUMBER;
````


## -struct-fields
<dl>

### -field <b>DeviceType</b>

<dd>
<p>Specifies one of the system-defined FILE_DEVICE_<i>XXX</i> constants indicating the type of device (such as FILE_DEVICE_DISK, FILE_DEVICE_KEYBOARD, and so forth) or a vendor-defined value for a new type of device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>. </p>
</dd>

### -field <b>DeviceNumber</b>

<dd>
<p>Indicates the number of this device. This value is set to 0xFFFFFFFF (-1) for the disks that represent the physical paths of an MPIO disk.</p>
</dd>

### -field <b>PartitionNumber</b>

<dd>
<p>Indicates the partition number of the device is returned in this member, if the device can be partitioned. Otherwise, -1 is returned. </p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560551">IOCTL_STORAGE_GET_DEVICE_NUMBER</a> request is usually issued by a fault-tolerant disk driver.</p>

<p>The values in the STORAGE_DEVICE_NUMBER structure are guaranteed to remain unchanged until the system is rebooted. They are not guaranteed to be persistent across boots.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560551">IOCTL_STORAGE_GET_DEVICE_NUMBER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20STORAGE_DEVICE_NUMBER structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>