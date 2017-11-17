---
UID: NS.ntddmmc._FEATURE_DATA_FORMATTABLE
title: FEATURE_DATA_FORMATTABLE
author: windows-driver-content
description: The FEATURE_DATA_FORMATTABLE structure contains information for the Formattable feature.
old-location: storage\feature_data_formattable.htm
ms.assetid: 658ea6a4-309d-4f78-9a02-f93e7d945325
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: Storage
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FEATURE_DATA_FORMATTABLE
req.alt-loc: ntddmmc.h
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
ms.keywords: FEATURE_DATA_FORMATTABLE, FEATURE_DATA_FORMATTABLE, *PFEATURE_DATA_FORMATTABLE
req.iface: 
---

# FEATURE_DATA_FORMATTABLE structure



## -description
<p>The FEATURE_DATA_FORMATTABLE structure contains information for the Formattable feature. </p>


## -syntax

````
typedef struct _FEATURE_DATA_FORMATTABLE {
  FEATURE_HEADER Header;
  UCHAR          FullCertification  :1;
  UCHAR          QuickCertification  :1;
  UCHAR          SpareAreaExpansion  :1;
  UCHAR          RENoSpareAllocated  :1;
  UCHAR          Reserved1  :4;
  UCHAR          Reserved2[3];
  UCHAR          RRandomWritable  :1;
  UCHAR          Reserved3  :7;
  UCHAR          Reserved4[3];
} FEATURE_DATA_FORMATTABLE, *PFEATURE_DATA_FORMATTABLE;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. </p>
</dd>

### -field <b>FullCertification</b>

<dd></dd>

### -field <b>QuickCertification</b>

<dd></dd>

### -field <b>SpareAreaExpansion</b>

<dd></dd>

### -field <b>RENoSpareAllocated</b>

<dd></dd>

### -field <b>Reserved1</b>

<dd></dd>

### -field <b>Reserved2</b>

<dd></dd>

### -field <b>RRandomWritable</b>

<dd></dd>

### -field <b>Reserved3</b>

<dd></dd>

### -field <b>Reserved4</b>

<dd></dd>
</dl>

## -remarks
<p>This structure holds data for the feature named "Formattable" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can format media into logical blocks. </p>

<p>When queried, devices supporting this feature must return the information indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>. No other feature-specific information is required. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddmmc.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20FEATURE_DATA_FORMATTABLE structure%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>