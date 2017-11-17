---
UID: NF.winddiui.DrvUpgradePrinter
title: DrvUpgradePrinter
author: windows-driver-content
description: A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system.
old-location: print\drvupgradeprinter.htm
ms.assetid: 5a8a764d-48bf-48f9-831a-ac22767aeca6
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: print
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrvUpgradePrinter
req.alt-loc: winddiui.h
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
ms.keywords: DrvUpgradePrinter
req.iface: 
req.product: Windows 10 or later.
---

# DrvUpgradePrinter function



## -description
<p>A printer interface DLL's <b>DrvUpgradePrinter</b> function is used for updating a printer's registry settings when a new version of the driver is added to a system.</p>


## -syntax

````
BOOL DrvUpgradePrinter(
           DWORD  Level,
  _In_opt_ LPBYTE pDriverUpgradeInfo
);
````


## -parameters
<dl>

### -param <i>Level</i> 

<dd>
<p>Caller-supplied value indicating the type of structure pointed to by <i>pDriverUpgradeInfo</i>, as indicated in the following table.</p>
<table>
<tr>
<th><i>Level</i> Value</th>
<th>Structure pointed to by <i>pDriverUpgradeInfo</i></th>
</tr>
<tr>
<td>
<p>1</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548522">DRIVER_UPGRADE_INFO_1</a>
</p>
</td>
</tr>
<tr>
<td>
<p>2</p>
</td>
<td>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548527">DRIVER_UPGRADE_INFO_2</a>
</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>pDriverUpgradeInfo</i> [in, optional]

<dd>
<p>Caller-supplied pointer to a structure whose type is identified by <i>dwLevel</i>. </p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function should return <b>TRUE</b>; otherwise, it should call SetLastError to set an error code and return <b>FALSE</b>.</p>

## -remarks
<p>A <a href="NULL">printer interface DLL</a> can optionally provide a <b>DrvUpgradePrinter</b> function. If it does, the spooler calls it for every printer when the printer driver is copied onto the system. This occurs when a system is upgraded from one operating system release to the next, or when an application updates a printer driver by calling the Win32 <b>AddPrinterDriver</b> function.</p>

<p>Often, a new driver version requires registry settings that are different from those of the old version. The <b>DrvUpgradePrinter</b> function's purpose is to update the registry so it is compatible with the driver. For more information about storing printer information in the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548564">DrvPrinterEvent</a>.</p>

<p>For Windows 2000 and later, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_2 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler calls the function again, this time specifying a DRIVER_UPGRADE_INFO_1 structure pointer. If this call returns <b>FALSE</b>, the spooler writes an entry in the event log.</p>

<p>For Windows NT 4.0 and previous, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_1 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler writes an entry in the event log.</p>

<p>A <a href="NULL">printer interface DLL</a> can optionally provide a <b>DrvUpgradePrinter</b> function. If it does, the spooler calls it for every printer when the printer driver is copied onto the system. This occurs when a system is upgraded from one operating system release to the next, or when an application updates a printer driver by calling the Win32 <b>AddPrinterDriver</b> function.</p>

<p>Often, a new driver version requires registry settings that are different from those of the old version. The <b>DrvUpgradePrinter</b> function's purpose is to update the registry so it is compatible with the driver. For more information about storing printer information in the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548564">DrvPrinterEvent</a>.</p>

<p>For Windows 2000 and later, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_2 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler calls the function again, this time specifying a DRIVER_UPGRADE_INFO_1 structure pointer. If this call returns <b>FALSE</b>, the spooler writes an entry in the event log.</p>

<p>For Windows NT 4.0 and previous, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_1 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler writes an entry in the event log.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winddiui.h (include Winddiui.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548564">DrvPrinterEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548522">DRIVER_UPGRADE_INFO_1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548527">DRIVER_UPGRADE_INFO_2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvUpgradePrinter function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>