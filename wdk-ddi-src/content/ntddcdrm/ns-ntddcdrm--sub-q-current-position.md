---
UID: NS.ntddcdrm._SUB_Q_CURRENT_POSITION
title: SUB_Q_CURRENT_POSITION
author: windows-driver-content
description: The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with SUB_Q_CHANNEL_DATA.
old-location: storage\sub_q_current_position.htm
ms.assetid: 816baec4-3dd0-4025-ba34-035bf6f241d3
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SUB_Q_CURRENT_POSITION
req.alt-loc: ntddcdrm.h
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
ms.keywords: SUB_Q_CURRENT_POSITION, SUB_Q_CURRENT_POSITION, *PSUB_Q_CURRENT_POSITION
req.iface: 
---

# SUB_Q_CURRENT_POSITION structure



## -description
<p>The SUB_Q_CURRENT_POSITION structure contains position information and is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>. </p>


## -syntax

````
typedef struct _SUB_Q_CURRENT_POSITION {
  SUB_Q_HEADER Header;
  UCHAR        FormatCode;
  UCHAR        Control  :4;
  UCHAR        ADR  :4;
  UCHAR        TrackNumber;
  UCHAR        IndexNumber;
  UCHAR        AbsoluteAddress[4];
  UCHAR        TrackRelativeAddress[4];
} SUB_Q_CURRENT_POSITION, *PSUB_Q_CURRENT_POSITION;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff567598">SUB_Q_HEADER</a> for more details. </p>
</dd>

### -field <b>FormatCode</b>

<dd>
<p>Should have a value of IOCTL_CDROM_CURRENT_POSITION. </p>
</dd>

### -field <b>Control</b>

<dd>
<p>Defines various types of information within the table of contents lead-in area. For more information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). </p>
</dd>

### -field <b>ADR</b>

<dd>
<p>Indicates the type of information encoded in the Q subchannel of the block. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS). </p>
</dd>

### -field <b>TrackNumber</b>

<dd>
<p>Contains the current track number.</p>
</dd>

### -field <b>IndexNumber</b>

<dd>
<p>Contains the current index number.</p>
</dd>

### -field <b>AbsoluteAddress</b>

<dd>
<p>Gives the current location relative to the logical beginning of the media. The bytes in this array are arranged in big-endian order. <b>AbsoluteAddress</b>[0] contains the most significant byte, and <b>AbsoluteAddress</b>[3] contains the least significant byte. </p>
</dd>

### -field <b>TrackRelativeAddress</b>

<dd>
<p>Gives the current location relative to the logical beginning of the current track. The bytes in this array are arranged in big-endian order. <b>TrackRelativeAddress</b>[0] contains the most significant byte, and <b>TrackRelativeAddress</b>[3] contains the least significant byte. </p>
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
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559363">IOCTL_CDROM_READ_Q_CHANNEL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551371">CDROM_SUB_Q_DATA_FORMAT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567595">SUB_Q_CHANNEL_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567598">SUB_Q_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SUB_Q_CURRENT_POSITION structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>