---
UID: NF.wdfdmatransaction.WdfDmaTransactionGetRequest
title: WdfDmaTransactionGetRequest
author: windows-driver-content
description: The WdfDmaTransactionGetRequest method retrieves a handle to the framework request object that is associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetrequest.htm
ms.assetid: 879bae2e-f608-4678-92ae-6100e59b6d52
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDmaTransactionGetRequest
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: WdfDmaTransactionGetRequest
req.iface: 
req.product: Windows 10 or later.
---

# WdfDmaTransactionGetRequest function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfDmaTransactionGetRequest</b> method retrieves a handle to the framework request object that is associated with a specified DMA transaction.</p>


## -syntax

````
WDFREQUEST WdfDmaTransactionGetRequest(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters
<dl>

### -param <i>DmaTransaction</i> [in]

<dd>
<p>A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.</p>
</dd>
</dl>

## -returns
<p><b>WdfDmaTransactionGetRequest</b> returns a handle to the framework request object that is associated with the DMA transaction that the <i>DmaTransaction</i> parameter specified.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>A driver can call <b>WdfDmaTransactionGetRequest</b> only for DMA transactions that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>. If a driver calls <b>WdfDmaTransactionGetRequest</b> for a DMA transaction that it created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>, <b>WdfDmaTransactionGetRequest</b> returns <b>NULL</b>.</p>

<p>For more information about completing DMA transfers, see <a href="NULL">Completing a DMA Transfer</a>. </p>

<p>The following code example obtains a handle to the framework request object that is associated with a specified DMA transaction.</p>

<p>A driver can call <b>WdfDmaTransactionGetRequest</b> only for DMA transactions that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>. If a driver calls <b>WdfDmaTransactionGetRequest</b> for a DMA transaction that it created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>, <b>WdfDmaTransactionGetRequest</b> returns <b>NULL</b>.</p>

<p>For more information about completing DMA transfers, see <a href="NULL">Completing a DMA Transfer</a>. </p>

<p>The following code example obtains a handle to the framework request object that is associated with a specified DMA transaction.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfdmatransaction.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547107">WdfDmaTransactionInitializeUsingRequest</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionGetRequest method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>