---
UID: NS.ntifs._TOKEN_GROUPS_AND_PRIVILEGES
title: TOKEN_GROUPS_AND_PRIVILEGES
author: windows-driver-content
description: TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.
old-location: ifsk\token_groups_and_privileges.htm
ms.assetid: 27d4793d-bdb4-46c5-b6e4-a2136e899adc
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
req.alt-api: TOKEN_GROUPS_AND_PRIVILEGES
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
ms.keywords: TOKEN_GROUPS_AND_PRIVILEGES, TOKEN_GROUPS_AND_PRIVILEGES, *PTOKEN_GROUPS_AND_PRIVILEGES
req.iface: 
---

# TOKEN_GROUPS_AND_PRIVILEGES structure



## -description
<p>TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token.</p>


## -syntax

````
typedef struct _TOKEN_GROUPS_AND_PRIVILEGES {
  ULONG                SidCount;
  ULONG                SidLength;
  PSID_AND_ATTRIBUTES  Sids;
  ULONG                RestrictedSidCount;
  ULONG                RestrictedSidLength;
  PSID_AND_ATTRIBUTES  RestrictedSids;
  ULONG                PrivilegeCount;
  ULONG                PrivilegeLength;
  PLUID_AND_ATTRIBUTES Privileges;
  LUID                 AuthenticationId;
} TOKEN_GROUPS_AND_PRIVILEGES, *PTOKEN_GROUPS_AND_PRIVILEGES;
````


## -struct-fields
<dl>

### -field <b>SidCount</b>

<dd>
<p>Specifies the number of SIDs in the access token. </p>
</dd>

### -field <b>SidLength</b>

<dd>
<p>Specifies the length, in bytes, required to hold all of the user SIDs and the account SID for the group. </p>
</dd>

### -field <b>Sids</b>

<dd>
<p>A pointer to SID_AND_ATTRIBUTES structures that contain a set of SIDs and corresponding attributes. </p>
</dd>

### -field <b>RestrictedSidCount</b>

<dd>
<p>Specifies the number of the restricted SIDs included in the access token. </p>
</dd>

### -field <b>RestrictedSidLength</b>

<dd>
<p>Specifies the length, in bytes, required to hold all of the restricted SIDs. </p>
</dd>

### -field <b>RestrictedSids</b>

<dd>
<p>A pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a> structures that contain a set of restricted SIDs and corresponding attributes. </p>
</dd>

### -field <b>PrivilegeCount</b>

<dd>
<p>Specifies the number of privileges included in the access token. </p>
</dd>

### -field <b>PrivilegeLength</b>

<dd>
<p>Specifies the length, in bytes, needed to hold all of the privileges. </p>
</dd>

### -field <b>Privileges</b>

<dd>
<p>A pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a> structures that contain a set of privileges. </p>
</dd>

### -field <b>AuthenticationId</b>

<dd>
<p>The locally unique identifier (LUID) of the authenticator of the token. </p>
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
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549716">LUID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556654">SeFilterToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556724">SeTokenIsRestricted</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556831">TOKEN_DEFAULT_DACL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556838">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556842">TOKEN_OWNER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556845">TOKEN_PRIMARY_GROUP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556846">TOKEN_PRIVILEGES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556848">TOKEN_SOURCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556849">TOKEN_STATISTICS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556851">TOKEN_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556855">TOKEN_USER</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_GROUPS_AND_PRIVILEGES structure%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>