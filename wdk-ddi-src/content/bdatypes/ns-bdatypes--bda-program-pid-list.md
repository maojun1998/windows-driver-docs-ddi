---
UID: NS.bdatypes._BDA_PROGRAM_PID_LIST
title: BDA_PROGRAM_PID_LIST
author: windows-driver-content
description: The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID).
old-location: stream\bda_program_pid_list.htm
ms.assetid: d3a96377-71f9-40ba-a15f-cacd64dcc6c4
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: bdatypes.h
req.include-header: Bdatypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_PROGRAM_PID_LIST
req.alt-loc: bdatypes.h
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
ms.keywords: BDA_PROGRAM_PID_LIST, BDA_PROGRAM_PID_LIST, *PBDA_PROGRAM_PID_LIST
req.iface: 
---

# BDA_PROGRAM_PID_LIST structure



## -description
<p>The BDA_PROGRAM_PID_LIST structure describes data of a specific program to view. This data consists of packets that are identified with packet identifiers (PID). </p>


## -syntax

````
typedef struct _BDA_PROGRAM_PID_LIST {
  ULONG ulProgramNumber;
  ULONG ulcPIDs;
  ULONG ulPID[MIN_DIMENSION];
} BDA_PROGRAM_PID_LIST, *PBDA_PROGRAM_PID_LIST;
````


## -struct-fields
<dl>

### -field <b>ulProgramNumber</b>

<dd>
<p>Number of the program to be viewed. </p>
</dd>

### -field <b>ulcPIDs</b>

<dd>
<p>Number of PIDs in the <b>ulPID</b> array. </p>
</dd>

### -field <b>ulPID</b>

<dd>
<p>Array of PIDs that identify packets of program data. </p>
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
<dt>Bdatypes.h (include Bdatypes.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564298">KSPROPERTY_BDA_CA_SET_PROGRAM_PIDS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566536">KSPROPSETID_BdaCA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_PROGRAM_PID_LIST structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>