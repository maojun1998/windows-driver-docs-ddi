---
UID: NE.rilapitypes.RILUICCAPPINFOPARAMMASK
title: RILUICCAPPINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappinfoparammask_2.htm
ms.assetid: 17ca9b1c-aaf9-434e-be60-5698aa159b48
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: netvista
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCAPPINFOPARAMMASK
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
ms.keywords: RIL_WritePhonebookEntry
req.iface: 
req.product: Windows 10 or later.
---

# RILUICCAPPINFOPARAMMASK enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef enum _RILUICCAPPINFOPARAMMASK { 
  RIL_PARAM_UICCAPPINFO_APPTYPE,
  RIL_PARAM_UICCAPPINFO_APPIDLENGTH,
  RIL_PARAM_UICCAPPINFO_APPID,
  RIL_PARAM_UICCAPPINFO_APPNAMELENGTH,
  RIL_PARAM_UICCAPPINFO_APPNAME,
  RIL_PARAM_UICCAPPINFO_NUMPINS,
  RIL_PARAM_UICCAPPINFO_PINREF,
  RIL_PARAM_UICCAPPINFO_ALL
} RILUICCAPPINFOPARAMMASK;
````


## -enum-fields
<dl>

### -field <a id="RIL_PARAM_UICCAPPINFO_APPTYPE"></a><a id="ril_param_uiccappinfo_apptype"></a><b>RIL_PARAM_UICCAPPINFO_APPTYPE</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_APPIDLENGTH"></a><a id="ril_param_uiccappinfo_appidlength"></a><b>RIL_PARAM_UICCAPPINFO_APPIDLENGTH</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_APPID"></a><a id="ril_param_uiccappinfo_appid"></a><b>RIL_PARAM_UICCAPPINFO_APPID</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_APPNAMELENGTH"></a><a id="ril_param_uiccappinfo_appnamelength"></a><b>RIL_PARAM_UICCAPPINFO_APPNAMELENGTH</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_APPNAME"></a><a id="ril_param_uiccappinfo_appname"></a><b>RIL_PARAM_UICCAPPINFO_APPNAME</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_NUMPINS"></a><a id="ril_param_uiccappinfo_numpins"></a><b>RIL_PARAM_UICCAPPINFO_NUMPINS</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_PINREF"></a><a id="ril_param_uiccappinfo_pinref"></a><b>RIL_PARAM_UICCAPPINFO_PINREF</b>

<dd></dd>

### -field <a id="RIL_PARAM_UICCAPPINFO_ALL"></a><a id="ril_param_uiccappinfo_all"></a><b>RIL_PARAM_UICCAPPINFO_ALL</b>

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