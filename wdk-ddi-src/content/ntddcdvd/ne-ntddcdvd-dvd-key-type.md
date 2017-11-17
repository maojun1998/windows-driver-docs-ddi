---
UID: NE.ntddcdvd.DVD_KEY_TYPE
title: DVD_KEY_TYPE
author: windows-driver-content
description: The DVD_KEY_TYPE enumeration type is used in conjunction with the DVD_COPY_PROTECT_KEY structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings.
old-location: storage\dvd_key_type.htm
ms.assetid: ec080043-a147-4002-8d0c-ed383182ec40
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DVD_KEY_TYPE
req.alt-loc: ntddcdvd.h
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
ms.keywords: VOLUME_CONTROL, VOLUME_CONTROL, *PVOLUME_CONTROL
req.iface: 
---

# DVD_KEY_TYPE enumeration



## -description
<p>The DVD_KEY_TYPE enumeration type is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a> structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings. </p>


## -syntax

````
typedef enum  { 
  DvdChallengeKey    = 0x01,
  DvdBusKey1         = 0x2,
  DvdBusKey2         = 0x3,
  DvdTitleKey        = 0x4,
  DvdAsf             = 0x5,
  DvdSetRpcKey       = 0x6,
  DvdGetRpcKey       = 0x8,
  DvdDiskKey         = 0x80,
  DvdInvalidateAGID  = 0x3f
} DVD_KEY_TYPE;
````


## -enum-fields
<dl>

### -field <a id="DvdChallengeKey"></a><a id="dvdchallengekey"></a><a id="DVDCHALLENGEKEY"></a><b>DvdChallengeKey</b>

<dd>
<p>Gets a challenge key. This is used during the authentication key exchange process.</p>
</dd>

### -field <a id="DvdBusKey1"></a><a id="dvdbuskey1"></a><a id="DVDBUSKEY1"></a><b>DvdBusKey1</b>

<dd>
<p>Gets the first bus key. </p>
</dd>

### -field <a id="DvdBusKey2"></a><a id="dvdbuskey2"></a><a id="DVDBUSKEY2"></a><b>DvdBusKey2</b>

<dd>
<p>Gets the second bus key. </p>
</dd>

### -field <a id="DvdTitleKey"></a><a id="dvdtitlekey"></a><a id="DVDTITLEKEY"></a><b>DvdTitleKey</b>

<dd>
<p>Gets a title key that is obfuscated by a bus key.</p>
</dd>

### -field <a id="DvdAsf"></a><a id="dvdasf"></a><a id="DVDASF"></a><b>DvdAsf</b>

<dd>
<p>Gets the current state of the authentication success flag (ASF).</p>
</dd>

### -field <a id="DvdSetRpcKey"></a><a id="dvdsetrpckey"></a><a id="DVDSETRPCKEY"></a><b>DvdSetRpcKey</b>

<dd>
<p>Sets the region playback contents (RPC) for the logical unit. </p>
</dd>

### -field <a id="DvdGetRpcKey"></a><a id="dvdgetrpckey"></a><a id="DVDGETRPCKEY"></a><b>DvdGetRpcKey</b>

<dd>
<p>Gets the region playback contents (RPC) for the logical unit. </p>
</dd>

### -field <a id="DvdDiskKey"></a><a id="dvddiskkey"></a><a id="DVDDISKKEY"></a><b>DvdDiskKey</b>

<dd>
<p>Gets the disc key. </p>
</dd>

### -field <a id="DvdInvalidateAGID"></a><a id="dvdinvalidateagid"></a><a id="DVDINVALIDATEAGID"></a><b>DvdInvalidateAGID</b>

<dd>
<p>Invalidates the specified authentication grant ID (AGID).</p>
</dd>
</dl>

## -remarks
<p>The driver for the DVD device uses the key type specified in this enumeration type to determine the key format in a report key command, as defined by the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification. A report key command can either report key data for a specified key (challenge key, bus key, title key, RPC key, or disc key), or the state of the ASF flag. It can also invalidate an AGID. See the <i>MMC-3 </i>specification for further information. </p>

<p>Drivers can issue a report key command to retrieve key data by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560425">IOCTL_DVD_READ_KEY</a> request. </p>

<p>The driver for the DVD device uses the key type specified in this enumeration type to determine the key format in a report key command, as defined by the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification. A report key command can either report key data for a specified key (challenge key, bus key, title key, RPC key, or disc key), or the state of the ASF flag. It can also invalidate an AGID. See the <i>MMC-3 </i>specification for further information. </p>

<p>Drivers can issue a report key command to retrieve key data by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560425">IOCTL_DVD_READ_KEY</a> request. </p>

<p>The driver for the DVD device uses the key type specified in this enumeration type to determine the key format in a report key command, as defined by the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification. A report key command can either report key data for a specified key (challenge key, bus key, title key, RPC key, or disc key), or the state of the ASF flag. It can also invalidate an AGID. See the <i>MMC-3 </i>specification for further information. </p>

<p>Drivers can issue a report key command to retrieve key data by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560425">IOCTL_DVD_READ_KEY</a> request. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddcdvd.h (include Ntddcdvd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560425">IOCTL_DVD_READ_KEY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560427">IOCTL_DVD_SEND_KEY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20DVD_KEY_TYPE enumeration%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>