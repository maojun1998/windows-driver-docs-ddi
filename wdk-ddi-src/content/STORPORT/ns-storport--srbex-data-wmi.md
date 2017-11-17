---
UID: NS.storport._SRBEX_DATA_WMI
title: SRBEX_DATA_WMI
author: windows-driver-content
description: The SRBEX_DATA_WMI structure contains the request data for an extended WMI SRB.
old-location: storage\srbex_data_wmi.htm
ms.assetid: 3FFBF258-50C3-4D2D-AFC8-184D2FF85EE4
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: storport.h
req.include-header: Storport.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available  starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRBEX_DATA_WMI
req.alt-loc: Storport.h
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
ms.keywords: SRBEX_DATA_WMI, SRBEX_DATA_WMI, *PSRBEX_DATA_WMI
req.iface: 
req.product: Windows 10 or later.
---

# SRBEX_DATA_WMI structure



## -description
<p>The <b>SRBEX_DATA_WMI</b> structure contains the request data for an extended WMI SRB.</p>


## -syntax

````
typedef struct _SRBEX_DATA_WMI {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               WMISubFunction;
  UCHAR               WMIFlags;
  UCHAR               Reserved[2];
  ULONG               Reserved1;
  PVOID POINTER_ALIGN DataPath;
} SRBEX_DATA_WMI, *PSRBEX_DATA_WMI;
````


## -struct-fields
<dl>

### -field <b>Type</b>

<dd>
<p>Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeWmi</b>.</p>
</dd>

### -field <b>Length</b>

<dd>
<p>Length of the data in this structure starting with the <b>WMISubFunction</b> member. Set to SRBEX_DATA_WMI_LENGTH.</p>
</dd>

### -field <b>WMISubFunction</b>

<dd>
<p>Indicates the WMI action to be performed. The subfunction value corresponds to the WMI minor IRP number that identifies the WMI operation. </p>
</dd>

### -field <b>WMIFlags</b>

<dd>
<p>Indicates that the WMI request is for the adapter if SRB_WMI_FLAGS_ADAPTER_REQUEST is set and that storage device address is reserved. Otherwise, <i>WMIFlags</i> will be <b>NULL</b>, indicating that the request is for the storage device specified by an address at <b>AddressOffset</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a> structure.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved. Contains zeros.</p>
</dd>

### -field <b>Reserved1</b>

<dd>
<p>This member is reserved. Set to 0.</p>
</dd>

### -field <b>DataPath</b>

<dd>
<p>Specifies the WMI data path for this request.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available  starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h or Srb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20SRBEX_DATA_WMI structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>