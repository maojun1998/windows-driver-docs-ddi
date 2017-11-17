---
UID: NC.dot11wdi.NDIS_WDI_TX_SEND_COMPLETE_IND
title: NDIS_WDI_TX_SEND_COMPLETE_IND
author: windows-driver-content
description: The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.
old-location: netvista\ndiswditxsendcompleteindication.htm
ms.assetid: A38BA15D-FDD8-41D1-87ED-2CABC1926962
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisWdiTxSendCompleteIndication
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

# NDIS_WDI_TX_SEND_COMPLETE_IND callback



## -description
<p>The NdisWdiTxSendCompleteIndication callback function specifies an array of frame IDs associated with the target's sent frames.</p>
<p>This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.</p>
<p>Frames with different TX status values are completed in separate indications.</p>


## -prototype

````
NDIS_WDI_TX_SEND_COMPLETE_IND NdisWdiTxSendCompleteIndication;

VOID NdisWdiTxSendCompleteIndication(
  _In_     NDIS_HANDLE          NdisMiniportDataPathHandle,
  _In_     WDI_TX_FRAME_STATUS  WifiTxFrameStatus,
  _In_     UINT16               NumCompletedSends,
  _In_     WDI_FRAME_ID         *WifiTxFrameIdList,
  _In_opt_ WDI_TX_COMPLETE_DATA *WifiTxCompleteList
)
{ ... }
````


## -parameters
<dl>

### -param <i>NdisMiniportDataPathHandle</i> [in]

<dd>
<p>The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.</p>
</dd>

### -param <i>WifiTxFrameStatus</i> [in]

<dd>
<p>The TX status, specified as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a> value.</p>
</dd>

### -param <i>NumCompletedSends</i> [in]

<dd>
<p>The number of completed sends.</p>
</dd>

### -param <i>WifiTxFrameIdList</i> [in]

<dd>
<p>An array of frame IDs. The size of the array is the value of <i>NumCompletedSends</i>.</p>
</dd>

### -param <i>WifiTxCompleteList</i> [in, optional]

<dd>
<p>An array of TX completion data. The size of the array is the value of <i>NumCompletedSends</i>.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn898193">WDI_TX_COMPLETE_DATA</a> is optional for all status values unless the indicated frames are sent over-the-air and have a status of <b>WDI_TxFrameStatus_SendPostponed</b>. In that case, <b>WDI_TX_COMPLETE_DATA</b> is required.</p>

<p>A TX completion with a frame with <b>WDI_TxFrameStatus_SendPostponed</b> is identical to an <a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a> with <b>WDI_TX_PAUSE_REASON_PS</b>.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn898193">WDI_TX_COMPLETE_DATA</a> is optional for all status values unless the indicated frames are sent over-the-air and have a status of <b>WDI_TxFrameStatus_SendPostponed</b>. In that case, <b>WDI_TX_COMPLETE_DATA</b> is required.</p>

<p>A TX completion with a frame with <b>WDI_TxFrameStatus_SendPostponed</b> is identical to an <a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a> with <b>WDI_TX_PAUSE_REASON_PS</b>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/A8001D08-36B8-4557-A763-103BDC807CA4">NdisWdiTxSendPauseIndication</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn898193">WDI_TX_COMPLETE_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn898194">WDI_TX_FRAME_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn898196">WDI_TX_PAUSE_REASON</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_SEND_COMPLETE_IND callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>