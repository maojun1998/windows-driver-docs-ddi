---
UID: NS.ntifs._TOKEN_GROUPS
title: TOKEN_GROUPS
author: windows-driver-content
description: TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token.
old-location: ifsk\token_groups.htm
ms.assetid: 08faebdf-7e6d-4da4-a4c2-a0b57de437ce
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TOKEN_GROUPS
req.alt-loc: ntifs.h
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
ms.keywords: TOKEN_GROUPS, TOKEN_GROUPS, *PTOKEN_GROUPS
req.iface: 
---

# TOKEN_GROUPS structure



## -description
<p>TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token. </p>


## -syntax

````
typedef struct _TOKEN_GROUPS {
  ULONG              GroupCount;
  SID_AND_ATTRIBUTES Groups[ANYSIZE_ARRAY];
} TOKEN_GROUPS, *PTOKEN_GROUPS;
````


## -struct-fields
<dl>

### -field <b>GroupCount</b>

<dd>
<p>Specifies the number of groups in the access token. </p>
</dd>

### -field <b>Groups</b>

<dd>
<p>Specifies an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a> structures containing a set of SIDs and corresponding attributes. </p>
</dd>
</dl>

## -remarks
<p>You can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a> to designate one or more group SIDs as deny-only SIDs. Note that it is also possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the <b>TOKEN_GROUPS</b> structure passed to <b>SeFilterToken</b>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567055">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567102">ZwSetInformationToken</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_GROUPS structure%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>