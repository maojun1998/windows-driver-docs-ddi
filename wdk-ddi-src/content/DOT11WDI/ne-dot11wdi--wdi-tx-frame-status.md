---
UID: NE.dot11wdi._WDI_TX_FRAME_STATUS
title: WDI_TX_FRAME_STATUS
author: windows-driver-content
description: The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values.
old-location: netvista\wdi_tx_frame_status.htm
ms.assetid: 6ea8a7ac-96dc-4337-884f-d30fbee1f760
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: netvista
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TX_FRAME_STATUS
req.alt-loc: dot11wdi.h
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
ms.keywords: SYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE
req.iface: ISynthSinkDMus
---

# WDI_TX_FRAME_STATUS enumeration



## -description
<p>The WDI_TX_FRAME_STATUS enumeration defines the TX frame status values.</p>


## -syntax

````
typedef enum _WDI_TX_FRAME_STATUS { 
  WDI_TxFrameStatus_Ok                 = 0,
  WDI_TxFrameStatus_Discard            = 1,
  WDI_TxFrameStatus_NoAck              = 2,
  WDI_TxFrameStatus_TransferCancelled  = 3,
  WDI_TxFrameStatus_SendCancelled      = 4,
  WDI_TxFrameStatus_SendPostponed      = 5,
  WDI_TxFrameStatus_TransferFailed     = 128
} WDI_TX_FRAME_STATUS;
````


## -enum-fields
<dl>

### -field <a id="WDI_TxFrameStatus_Ok"></a><a id="wdi_txframestatus_ok"></a><a id="WDI_TXFRAMESTATUS_OK"></a><b>WDI_TxFrameStatus_Ok</b>

<dd>
<p>Frame transmitted without errors.</p>
</dd>

### -field <a id="WDI_TxFrameStatus_Discard"></a><a id="wdi_txframestatus_discard"></a><a id="WDI_TXFRAMESTATUS_DISCARD"></a><b>WDI_TxFrameStatus_Discard</b>

<dd>
<p>The frame was discarded to make room for higher priority frames.</p>
</dd>

### -field <a id="WDI_TxFrameStatus_NoAck"></a><a id="wdi_txframestatus_noack"></a><a id="WDI_TXFRAMESTATUS_NOACK"></a><b>WDI_TxFrameStatus_NoAck</b>

<dd>
<p>Transmission failed after exhausting the maximum number of retries.</p>
</dd>

### -field <a id="WDI_TxFrameStatus_TransferCancelled"></a><a id="wdi_txframestatus_transfercancelled"></a><a id="WDI_TXFRAMESTATUS_TRANSFERCANCELLED"></a><b>WDI_TxFrameStatus_TransferCancelled</b>

<dd>
<p>TX stop requested.</p>
</dd>

### -field <a id="WDI_TxFrameStatus_SendCancelled"></a><a id="wdi_txframestatus_sendcancelled"></a><a id="WDI_TXFRAMESTATUS_SENDCANCELLED"></a><b>WDI_TxFrameStatus_SendCancelled</b>

<dd>
<p>TX stop requested.</p>
</dd>

### -field <a id="WDI_TxFrameStatus_SendPostponed"></a><a id="wdi_txframestatus_sendpostponed"></a><a id="WDI_TXFRAMESTATUS_SENDPOSTPONED"></a><b>WDI_TxFrameStatus_SendPostponed</b>

<dd>
<p>The frame could not be transmitted at this time (for example, the peer is in PS). The frame should be transferred at a suitable time, when the corresponding TX queue is unpaused. This status is not allowed for targets that have <b>TargetPriorityQueueing</b> set to TRUE.</p>
</dd>

### -field <a id="WDI_TxFrameStatus_TransferFailed"></a><a id="wdi_txframestatus_transferfailed"></a><a id="WDI_TXFRAMESTATUS_TRANSFERFAILED"></a><b>WDI_TxFrameStatus_TransferFailed</b>

<dd>
<p>The transfer failed.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn898187">WDI_TXRX_CAPABILITIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_TX_FRAME_STATUS enumeration%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>