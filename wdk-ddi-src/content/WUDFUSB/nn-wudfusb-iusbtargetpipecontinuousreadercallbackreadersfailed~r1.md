---
UID: NN.wudfusb.IUsbTargetPipeContinuousReaderCallbackReadersFailed~r1
title: IUsbTargetPipeContinuousReaderCallbackReadersFailed
author: windows-driver-content
description: IUsbTargetPipeContinuousReaderCallbackReadersFailed is a driver-supplied interface.
old-location: wdf\iusbtargetpipecontinuousreadercallbackreadersfailed.htm
ms.assetid: d0b68976-f7aa-4b0d-b6bb-258ad2c2e506
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfusb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IUsbTargetPipeContinuousReaderCallbackReadersFailed
req.alt-loc: wudfusb.h
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
ms.keywords: IWDFUsbTargetPipe2, ConfigureContinuousReader, IWDFUsbTargetPipe2::ConfigureContinuousReader
req.iface: IWDFUsbTargetPipe2
req.product: Windows 10 or later.
---

# IUsbTargetPipeContinuousReaderCallbackReadersFailed interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>
<p><b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> is a driver-supplied interface.</p>
</p>
<p><b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> is a driver-supplied interface.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> also has these types of members:</p>

<p>The <b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> interface has these methods.</p>

<p>A driver's <a href="https://msdn.microsoft.com/ad91208e-e57a-4b80-b1a1-13b9f7eb1119">OnReaderFailure</a> event callback function informs the driver that a continuous reader has reported an error while processing a read request.</p>

<p> </p>

## -members
<p>The <b>IUsbTargetPipeContinuousReaderCallbackReadersFailed</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556915">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a>
</td>
<td align="left" width="63%">
<p>A driver's <a href="https://msdn.microsoft.com/ad91208e-e57a-4b80-b1a1-13b9f7eb1119">OnReaderFailure</a> event callback function informs the driver that a continuous reader has reported an error while processing a read request.</p>
</td>
</tr>
</table><p>A driver's <a href="https://msdn.microsoft.com/ad91208e-e57a-4b80-b1a1-13b9f7eb1119">OnReaderFailure</a> event callback function informs the driver that a continuous reader has reported an error while processing a read request.</p>

<p> </p>

## -remarks


## -requirements
<table>
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
</table>