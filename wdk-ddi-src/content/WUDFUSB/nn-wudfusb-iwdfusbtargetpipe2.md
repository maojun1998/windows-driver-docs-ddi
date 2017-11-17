---
UID: NN.wudfusb.IWDFUsbTargetPipe2
title: IWDFUsbTargetPipe2
author: windows-driver-content
description: The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.
old-location: wdf\iwdfusbtargetpipe2.htm
ms.assetid: c3df39cb-17f4-4f68-bde3-f53ba40dde85
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfusb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFUsbTargetPipe2
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
ms.keywords: IWDFUsbTargetPipe2, ConfigureContinuousReader, IWDFUsbTargetPipe2::ConfigureContinuousReader
req.iface: IWDFUsbTargetPipe2
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe2 interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>
<p>The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.</p>
</p>
<p>The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetPipe2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>. <b>IWDFUsbTargetPipe2</b> also has these types of members:</p>

<p>The <b>IWDFUsbTargetPipe2</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/accb2690-0ab7-4623-8493-545e6e722a7a">ConfigureContinuousReader</a> method configures the framework to continuously read from a USB pipe.</p>

<p> </p>

## -members
<p>The <b>IWDFUsbTargetPipe2</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560395">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/accb2690-0ab7-4623-8493-545e6e722a7a">ConfigureContinuousReader</a> method configures the framework to continuously read from a USB pipe.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/accb2690-0ab7-4623-8493-545e6e722a7a">ConfigureContinuousReader</a> method configures the framework to continuously read from a USB pipe.</p>

<p> </p>

## -remarks
<p>Drivers obtain the <b>IWDFUsbTargetPipe2</b> interface by calling <b>IWDFUsbTargetPipe::QueryInterface</b>.</p>

<p>Drivers obtain the <b>IWDFUsbTargetPipe2</b> interface by calling <b>IWDFUsbTargetPipe::QueryInterface</b>.</p>

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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfusb.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>