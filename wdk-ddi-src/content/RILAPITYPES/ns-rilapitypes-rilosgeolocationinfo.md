---
UID: NS.rilapitypes.RILOSGEOLOCATIONINFO
title: RILOSGEOLOCATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilosgeolocationinfo_2.htm
ms.assetid: 5207e880-67cb-4cd5-9884-a01e6dd20201
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILOSGEOLOCATIONINFO
req.alt-loc: rilapitypes.h
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
ms.keywords: RILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO
req.iface: 
req.product: Windows 10 or later.
---

# RILOSGEOLOCATIONINFO structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILOSGEOLOCATIONINFO {
  DWORD                              cbSize;
  DWORD                              dwParams;
  DWORD                              dwLatitude;
  DWORD                              dwLongitude;
  DWORD                              dwAltitude;
  DWORD                              dwAccuracy;
  RILGEOLOCATIONTYPEMASK             dwLocationInformationMask;
  RILSYSTEMTIME                      stTimeStamp;
  WCHAR [MAXLENGTH_ADDRESS1]         wszAddressLine1;
  WCHAR [MAXLENGTH_ADDRESS2]         wszAddressLine2;
  WCHAR [MAXLENGTH_CITY]             wszCity;
  WCHAR [MAXLENGTH_STATE]            wszState;
  WCHAR [MAXLENGTH_COUNTRY]          wszCountry;
  WCHAR [MAXLENGTH_ZIP]              wszPostalCode;
  WCHAR [MAXLENGTH_FORMATTEDADDRESS] wszFormattedAddress;
  WCHAR [MAXLENGTH_COUNTRYCODE]      wszCountryCode;
  WCHAR [MAXLENGTH_REGIONCODE]       wszRegionCode;
} RILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwParams</b>

<dd></dd>

### -field <b>dwLatitude</b>

<dd></dd>

### -field <b>dwLongitude</b>

<dd></dd>

### -field <b>dwAltitude</b>

<dd></dd>

### -field <b>dwAccuracy</b>

<dd></dd>

### -field <b>dwLocationInformationMask</b>

<dd></dd>

### -field <b>stTimeStamp</b>

<dd></dd>

### -field <b>wszAddressLine1</b>

<dd></dd>

### -field <b>wszAddressLine2</b>

<dd></dd>

### -field <b>wszCity</b>

<dd></dd>

### -field <b>wszState</b>

<dd></dd>

### -field <b>wszCountry</b>

<dd></dd>

### -field <b>wszPostalCode</b>

<dd></dd>

### -field <b>wszFormattedAddress</b>

<dd></dd>

### -field <b>wszCountryCode</b>

<dd></dd>

### -field <b>wszRegionCode</b>

<dd></dd>
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
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>