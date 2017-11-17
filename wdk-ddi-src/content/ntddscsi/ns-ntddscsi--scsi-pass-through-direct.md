---
UID: NS.ntddscsi._SCSI_PASS_THROUGH_DIRECT
title: SCSI_PASS_THROUGH_DIRECT
author: windows-driver-content
description: The SCSI_PASS_THROUGH_DIRECT structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct.htm
ms.assetid: 306babe7-393f-4b4a-9d8a-4c973cb3eaa2
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_PASS_THROUGH_DIRECT
req.alt-loc: ntddscsi.h
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
ms.keywords: SCSI_PASS_THROUGH_DIRECT, SCSI_PASS_THROUGH_DIRECT, *PSCSI_PASS_THROUGH_DIRECT
req.iface: 
---

# SCSI_PASS_THROUGH_DIRECT structure



## -description
<p>The <b>SCSI_PASS_THROUGH_DIRECT</b> structure is used in conjunction with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a> request to instruct the port driver to send an embedded SCSI command to the target device. </p>


## -syntax

````
typedef struct _SCSI_PASS_THROUGH_DIRECT {
  USHORT Length;
  UCHAR  ScsiStatus;
  UCHAR  PathId;
  UCHAR  TargetId;
  UCHAR  Lun;
  UCHAR  CdbLength;
  UCHAR  SenseInfoLength;
  UCHAR  DataIn;
  ULONG  DataTransferLength;
  ULONG  TimeOutValue;
  PVOID  DataBuffer;
  ULONG  SenseInfoOffset;
  UCHAR  Cdb[16];
} SCSI_PASS_THROUGH_DIRECT, *PSCSI_PASS_THROUGH_DIRECT;
````


## -struct-fields
<dl>

### -field <b>Length</b>

<dd>
<p>Contains the value of <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT).  </p>
</dd>

### -field <b>ScsiStatus</b>

<dd>
<p>Reports the SCSI status that was returned by the HBA or the target device. </p>
</dd>

### -field <b>PathId</b>

<dd>
<p>Indicates the SCSI port or bus for the request. </p>
</dd>

### -field <b>TargetId</b>

<dd>
<p>Indicates the target controller or device on the bus.  </p>
</dd>

### -field <b>Lun</b>

<dd>
<p>Indicates the logical unit number of the device. </p>
</dd>

### -field <b>CdbLength</b>

<dd>
<p>Indicates the size in bytes of the SCSI command descriptor block. </p>
</dd>

### -field <b>SenseInfoLength</b>

<dd>
<p>Indicates the size in bytes of the request-sense buffer. </p>
</dd>

### -field <b>DataIn</b>

<dd>
<dl>

### -field Indicates whether the SCSI command will read or write data. This field must have one of three values:


### -field 
<p>
<table>
<tr>
<th>Data Transfer Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>SCSI_IOCTL_DATA_IN</p>
</td>
<td>
<p>Read data from the device.</p>
</td>
</tr>
<tr>
<td>
<p>SCSI_IOCTL_DATA_OUT</p>
</td>
<td>
<p>Write data to the device.</p>
</td>
</tr>
<tr>
<td>
<p>SCSI_IOCTL_DATA_UNSPECIFIED</p>
</td>
<td>
<p>No data transferred.  </p>
</td>
</tr>
</table>
<p> </p>
</p>


</dl>
</dd>

### -field <b>DataTransferLength</b>

<dd>
<p>Indicates the size in bytes of the data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.</p>
</dd>

### -field <b>TimeOutValue</b>

<dd>
<p>Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out.</p>
</dd>

### -field <b>DataBuffer</b>

<dd>
<p>Pointer to the data buffer. </p>
</dd>

### -field <b>SenseInfoOffset</b>

<dd>
<p>Contains an offset from the beginning of this structure to the request-sense buffer. </p>
</dd>

### -field <b>Cdb</b>

<dd>
<p>Specifies the SCSI command descriptor block to be sent to the target device. </p>
</dd>
</dl>

## -remarks
<p>The SCSI_PASS_THROUGH_DIRECT structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>. With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a>.</p>

<p>The members of SCSI_PASS_THROUGH_DIRECT correspond roughly to the members of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> structure. The values of the <b>DataIn</b> member correspond to the SCSI_IOCTL_DATA_IN, SCSI_IOCTL_DATA_OUT, and SCSI_IOCTL_DATA_UNSPECIFIED flags assigned to <b>SrbFlags</b> member of SCSI_REQUEST_BLOCK. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h (include Ntddscsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560519">IOCTL_SCSI_PASS_THROUGH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565345">SCSI_PASS_THROUGH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SCSI_PASS_THROUGH_DIRECT structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>