---
UID: NS.1394._SPEED_MAP
title: SPEED_MAP
author: windows-driver-content
description: The SPEED_MAP structure is stores a IEEE 1394 bus speed map.
old-location: ieee\speed_map.htm
ms.assetid: 52b2b97e-217b-445b-9c7a-093808f37aba
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: IEEE
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPEED_MAP
req.alt-loc: 1394.h
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
ms.keywords: SPEED_MAP, SPEED_MAP, *PSPEED_MAP
---

# SPEED_MAP structure



## -description
<p>The SPEED_MAP structure is stores a IEEE 1394 bus speed map.</p>


## -syntax

````
typedef struct _SPEED_MAP {
  USHORT SPD_Length;
  USHORT SPD_CRC;
  ULONG  SPD_Generation;
  UCHAR  SPD_Speed_Code[4032];
} SPEED_MAP, *PSPEED_MAP;
````


## -struct-fields
<dl>

### -field <b>SPD_Length</b>

<dd>
<p>Specifies the number of quadlets in the speed map.</p>
</dd>

### -field <b>SPD_CRC</b>

<dd>
<p>Specifies the CRC value for the speed map.</p>
</dd>

### -field <b>SPD_Generation</b>

<dd>
<p>Specifies the generation count for the bus reset that corresponds to this speed map.</p>
</dd>

### -field <b>SPD_Speed_Code</b>

<dd>
<p>Specifies an array of speed codes. Currently, the possible values are:</p>
<dl>
<dd>
<p>SCODE_100_RATE</p>
</dd>
<dd>
<p>SCODE_200_RATE</p>
</dd>
<dd>
<p>SCODE_400_RATE</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The SPEED_MAP structure describes the maximum speed that devices on the bus can attain. All values in this structure are recorded in big-endian format.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>1394.h (include 1394.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537646">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SPEED_MAP structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>