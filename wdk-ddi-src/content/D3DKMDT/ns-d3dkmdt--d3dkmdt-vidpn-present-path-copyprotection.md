---
UID: NS.d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
title: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection.htm
ms.assetid: 661e70c6-d99e-4c5a-ad88-3dd854747de4
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
req.alt-loc: d3dkmdt.h
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
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
req.iface: 
---

# D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure



## -description
<p>The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.</p>


## -syntax

````
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION {
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE    CopyProtectionType;
  UINT                                              APSTriggerBits;
  BYTE                                              OEMCopyProtection[D3DKMDT_MACROVISION_OEMCOPYPROTECTION_SIZE];
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT CopyProtectionSupport;
} D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION;
````


## -struct-fields
<dl>

### -field <b>CopyProtectionType</b>

<dd>
<p>A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546692">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE</a> enumeration that indicates the type of copy protection that is active on the path.</p>
</dd>

### -field <b>APSTriggerBits</b>

<dd>
<p>A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.</p>
</dd>

### -field <b>OEMCopyProtection</b>

<dd>
<p>Reserved for future use.</p>
</dd>

### -field <b>CopyProtectionSupport</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546677">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT</a> structure that indicates the types of copy protection that are supported by the path.</p>
</dd>
</dl>

## -remarks
<p>The <b>CopyProtection</b> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>