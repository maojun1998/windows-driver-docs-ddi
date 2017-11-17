---
UID: NE.windot11._DOT11_WFD_SCAN_TYPE
title: DOT11_WFD_SCAN_TYPE
author: windows-driver-content
description: The DOT11_WFD_SCAN_TYPE enumeration indicates the type of scan used during the scan phase of device discovery.
old-location: netvista\dot11_wfd_scan_type.htm
ms.assetid: E7F76E93-79B8-48AE-A1D1-E3215E2402F8
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: netvista
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_SCAN_TYPE
req.alt-loc: Windot11.h
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
ms.keywords: PRINTER_EVENT_ATTRIBUTES_INFO, PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.iface: 
req.product: Windows 10 or later.
---

# DOT11_WFD_SCAN_TYPE enumeration



## -description

## -syntax

````
typedef enum _DOT11_WFD_SCAN_TYPE { 
  dot11_wfd_scan_type_active   = 1,
  dot11_wfd_scan_type_passive  = 2,
  dot11_wfd_scan_type_auto     = 3
} DOT11_WFD_SCAN_TYPE;
````


## -enum-fields
<dl>

### -field <a id="dot11_wfd_scan_type_active"></a><a id="DOT11_WFD_SCAN_TYPE_ACTIVE"></a><b>dot11_wfd_scan_type_active</b>

<dd>
<p>Use active scanning for device discovery.</p>
</dd>

### -field <a id="dot11_wfd_scan_type_passive"></a><a id="DOT11_WFD_SCAN_TYPE_PASSIVE"></a><b>dot11_wfd_scan_type_passive</b>

<dd>
<p>Use passive scanning during device discovery.</p>
</dd>

### -field <a id="dot11_wfd_scan_type_auto"></a><a id="DOT11_WFD_SCAN_TYPE_AUTO"></a><b>dot11_wfd_scan_type_auto</b>

<dd>
<p>Driver selected scanning is used.</p>
</dd>
</dl>

## -remarks
<p>The system will set only one scan type at a time. The driver should use this setting to determine how it scans during device discovery.</p>

<p>The system will set only one scan type at a time. The driver should use this setting to determine how it scans during device discovery.</p>

<p>The system will set only one scan type at a time. The driver should use this setting to determine how it scans during device discovery.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with  Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/231318AA-9112-41E2-9E7A-FEC64E5FB30A">DOT11_WFD_DISCOVER_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451795">OID_DOT11_WFD_DISCOVER_REQUEST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_WFD_SCAN_TYPE enumeration%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>