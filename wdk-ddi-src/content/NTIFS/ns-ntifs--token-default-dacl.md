---
UID: NS.ntifs._TOKEN_DEFAULT_DACL
title: TOKEN_DEFAULT_DACL
author: windows-driver-content
description: The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL).
old-location: ifsk\token_default_dacl.htm
ms.assetid: db4c23e1-4a49-4864-9eab-36abb2581e58
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
req.alt-api: TOKEN_DEFAULT_DACL
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
ms.keywords: TOKEN_DEFAULT_DACL, TOKEN_DEFAULT_DACL, *PTOKEN_DEFAULT_DACL
req.iface: 
---

# TOKEN_DEFAULT_DACL structure



## -description
<p>The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL). </p>


## -syntax

````
typedef struct _TOKEN_DEFAULT_DACL {
  PACL DefaultDacl;
} TOKEN_DEFAULT_DACL, *PTOKEN_DEFAULT_DACL;
````


## -struct-fields
<dl>

### -field <b>DefaultDacl</b>

<dd>
<p>Pointer to an access control list (ACL) structure assigned by default to any objects created by the user represented by the access token. </p>
</dd>
</dl>

## -remarks
<p>The <b>SeQueryInformationToken</b> support routine retrieves the default DACL for an access token, in the form of a TOKEN_DEFAULT_DACL structure. </p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556690">SeQueryInformationToken</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_DEFAULT_DACL structure%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>