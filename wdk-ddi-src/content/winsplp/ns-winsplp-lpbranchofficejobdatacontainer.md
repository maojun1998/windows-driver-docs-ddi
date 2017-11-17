---
UID: NS.winsplp.LPBranchOfficeJobDataContainer
title: LPBranchOfficeJobDataContainer
author: windows-driver-content
description: This structure defines a container for one or more BranchOfficeJobData structures to sent to a server.
old-location: print\branchofficejobdatacontainer.htm
ms.assetid: 5C6D2FFC-DBFF-4C44-8757-ED87593A584F
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: print
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BranchOfficeJobDataContainer
req.alt-loc: Winsplp.h
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
ms.keywords: LPBranchOfficeJobDataContainer, BranchOfficeJobDataContainer, *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer
req.iface: 
req.product: Windows 10 or later.
---

# LPBranchOfficeJobDataContainer structure



## -description
<p>This structure defines a container for one or more <a href="RID">BranchOfficeJobData</a> structures to sent to a server.</p>


## -syntax

````
typedef struct {
  DWORD               cJobDataEntries;
  BranchOfficeJobData JobData[1];
} BranchOfficeJobDataContainer, *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer;
````


## -struct-fields
<dl>

### -field <b>cJobDataEntries</b>

<dd>
<p>Describes the <b>DWORD</b> type member <b>cJobDataEntries</b>.</p>
</dd>

### -field <b>JobData</b>

<dd>
<p>Describes the <b>BranchOfficeJobData</b> type member <b>JobData</b>.</p>
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
<dt>Winsplp.h</dt>
</dl>
</td>
</tr>
</table>