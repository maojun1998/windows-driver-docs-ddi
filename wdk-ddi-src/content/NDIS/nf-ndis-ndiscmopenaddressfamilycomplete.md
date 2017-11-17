---
UID: NF.ndis.NdisCmOpenAddressFamilyComplete
title: NdisCmOpenAddressFamilyComplete
author: windows-driver-content
description: NdisCmOpenAddressFamilyComplete returns the final status of a stand-alone call manager's open of a given AF for a particular client after the call manager returned NDIS_STATUS_PENDING in response to that client's original open-AF request.
old-location: netvista\ndiscmopenaddressfamilycomplete.htm
ms.assetid: eed57341-0b1a-4697-b05d-680bc17da796
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   
   NdisCmOpenAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   
   NdisCmOpenAddressFamilyComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmOpenAddressFamilyComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_CallManager_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: NdisCmOpenAddressFamilyComplete
req.iface: 
---

# NdisCmOpenAddressFamilyComplete function



## -description
<p><b>NdisCmOpenAddressFamilyComplete</b> returns the final status of a stand-alone call manager's open of a
  given AF for a particular client after the call manager returned NDIS_STATUS_PENDING in response to that
  client's original open-AF request.</p>


## -syntax

````
VOID NdisCmOpenAddressFamilyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisAfHandle,
  _In_ NDIS_HANDLE CallMgrAfContext
);
````


## -parameters
<dl>

### -param <i>Status</i> [in]

<dd>
<p>Specifies the final status of the open-AF operation, either NDIS_STATUS_SUCCESS or any
     CM-determined error NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.</p>
</dd>

### -param <i>NdisAfHandle</i> [in]

<dd>
<p>Specifies the NDIS-supplied handle that was input to the call manager's 
     <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function, which
     returned NDIS_STATUS_PENDING.</p>
</dd>

### -param <i>CallMgrAfContext</i> [in]

<dd>
<p>Specifies the handle to a caller-allocated resident context area in which the call manager
     maintains state about this client's open of the address family, including the 
     <i>NdisAfHandle</i>, if the open succeeded. If 
     <i>Status</i> is not NDIS_STATUS_SUCCESS, NDIS ignores this parameter.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A stand-alone call manager must call 
    <b>NdisCmOpenAddressFamilyComplete</b> if its 
    <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended open-AF operation with a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>,
    cannot carry out further connection-oriented operations on the same binding until 
    <b>NdisCmOpenAddressFamilyComplete</b> causes a call to that client's 
    <a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">
    ProtocolClOpenAfCompleteEx</a> function.</p>

<p>If the caller of 
    <b>NdisCmOpenAddressFamilyComplete</b> sets 
    <i>Status</i> to NDIS_STATUS_SUCCESS, NDIS subsequently passes the given 
    <i>CallMgrAfContext</i> handle as an input parameter to all CM-supplied ProtocolCm<i>Xxx</i> and ProtocolCo<i>Xxx</i> functions that concern the client's open of the address family until the client closes the AF.
    The call manager should release or reuse any AF context area that it allocated before it passes a failure
    status to 
    <b>NdisCmOpenAddressFamilyComplete</b>.</p>

<p>For a successful open, the NDIS-supplied 
    <i>NdisAfHandle</i> represents an association between the call manager and client for the opened AF on a
    particular miniport driver to which the call manager and client are bound. Both protocol drivers must
    treat 
    <i>NdisAfHandle</i> as an opaque variable to be passed, unmodified and uninterpreted, in subsequent calls
    to NdisCl/Cm/CoXxx functions for which this handle is a required parameter. For a failed open, the call
    manager should consider the 
    <i>NdisAfHandle</i> invalid when 
    <b>NdisMCmOpenAddressFamilyComplete</b> returns control.</p>

<p>Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmOpenAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <a href="https://msdn.microsoft.com/e2d6c7db-09b3-4e5a-a6da-607c67e03054">
    NdisMCmOpenAddressFamilyComplete</a> instead.</p>

<p>A stand-alone call manager must call 
    <b>NdisCmOpenAddressFamilyComplete</b> if its 
    <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended open-AF operation with a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>,
    cannot carry out further connection-oriented operations on the same binding until 
    <b>NdisCmOpenAddressFamilyComplete</b> causes a call to that client's 
    <a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">
    ProtocolClOpenAfCompleteEx</a> function.</p>

<p>If the caller of 
    <b>NdisCmOpenAddressFamilyComplete</b> sets 
    <i>Status</i> to NDIS_STATUS_SUCCESS, NDIS subsequently passes the given 
    <i>CallMgrAfContext</i> handle as an input parameter to all CM-supplied ProtocolCm<i>Xxx</i> and ProtocolCo<i>Xxx</i> functions that concern the client's open of the address family until the client closes the AF.
    The call manager should release or reuse any AF context area that it allocated before it passes a failure
    status to 
    <b>NdisCmOpenAddressFamilyComplete</b>.</p>

<p>For a successful open, the NDIS-supplied 
    <i>NdisAfHandle</i> represents an association between the call manager and client for the opened AF on a
    particular miniport driver to which the call manager and client are bound. Both protocol drivers must
    treat 
    <i>NdisAfHandle</i> as an opaque variable to be passed, unmodified and uninterpreted, in subsequent calls
    to NdisCl/Cm/CoXxx functions for which this handle is a required parameter. For a failed open, the call
    manager should consider the 
    <i>NdisAfHandle</i> invalid when 
    <b>NdisMCmOpenAddressFamilyComplete</b> returns control.</p>

<p>Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmOpenAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <a href="https://msdn.microsoft.com/e2d6c7db-09b3-4e5a-a6da-607c67e03054">
    NdisMCmOpenAddressFamilyComplete</a> instead.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/77680fd1-94f2-41f7-a926-061c652f3a3e">
   NdisCmOpenAddressFamilyComplete (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisCmOpenAddressFamilyComplete (NDIS 5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547917">Irql_CallManager_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e2d6c7db-09b3-4e5a-a6da-607c67e03054">
   NdisMCmOpenAddressFamilyComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">ProtocolClOpenAfCompleteEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmOpenAddressFamilyComplete function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>