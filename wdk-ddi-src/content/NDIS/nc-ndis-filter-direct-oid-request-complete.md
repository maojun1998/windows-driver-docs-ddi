---
UID: NC.ndis.FILTER_DIRECT_OID_REQUEST_COMPLETE
title: FILTER_DIRECT_OID_REQUEST_COMPLETE
author: windows-driver-content
description: NDIS calls the FilterDirectOidRequestComplete function to complete a filter driver direct OID request that queried or set information in an underlying driver.Note  You must declare the function by using the FILTER_DIRECT_OID_REQUEST_COMPLETE type.
old-location: netvista\filterdirectoidrequestcomplete.htm
ms.assetid: a97c86e9-4fd9-4e2f-9787-4fa19c38a69b
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FilterDirectOidRequestComplete
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: RxNameCacheInitialize
req.iface: 
---

# FILTER_DIRECT_OID_REQUEST_COMPLETE callback



## -description
<p>NDIS calls the 
  <i>FilterDirectOidRequestComplete</i> function to complete a filter driver direct OID request that queried
  or set information in an underlying driver.</p>


## -prototype

````
FILTER_DIRECT_OID_REQUEST_COMPLETE FilterDirectOidRequestComplete;

VOID FilterDirectOidRequestComplete(
  _In_ NDIS_HANDLE       FilterModuleContext,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
)
{ ... }
````


## -parameters
<dl>

### -param <i>FilterModuleContext</i> [in]

<dd>
<p>A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.</p>
</dd>

### -param <i>OidRequest</i> [in]

<dd>
<p>A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that the filter
     driver previously passed to the 
     <a href="https://msdn.microsoft.com/dec5415b-6903-416e-819b-007ea6f7e7b5">
     NdisFDirectOidRequest</a> function.</p>
</dd>

### -param <i>Status</i> [in]

<dd>
<p>The final status of the request that an underlying driver or NDIS set. This parameter determines
     what 
     <i>FilterDirectOidRequestComplete</i> does with the information at 
     <i>OidRequest</i> . For a list of the possible status values, see the return values of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><i>FilterDirectOidRequestComplete</i> is an optional function. If a filter driver does not use direct OID
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function. If a filter driver defines a 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function,
    it must provide the 
    <i>FilterDirectOidRequestComplete</i> function.</p>

<p>If the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a> function
    returns NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterDirectOidRequestComplete</i> function to complete the OID request.</p>

<p>If a filter driver forwarded a request that it received in the 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function,
    
    <i>FilterDirectOidRequestComplete</i> should pass the completion status up the driver stack by calling the
    
    <a href="https://msdn.microsoft.com/b6b4d4f4-63d5-496c-9082-f2e8d1a174ec">
    NdisFDirectOidRequestComplete</a> function. In this case, the filter driver must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a>, to free
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure, before it calls
    
    <b>NdisFDirectOidRequestComplete</b>.</p>

<p>A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFDirectOidRequestComplete</b> when NDIS calls 
    <i>FilterDirectOidRequestComplete</i> for such requests.</p>

<p>NDIS calls 
    <i>FilterDirectOidRequestComplete</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>FilterDirectOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>FilterDirectOidRequestComplete</i> function that is named "MyDirectOidRequestComplete", use the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

<p><i>FilterDirectOidRequestComplete</i> is an optional function. If a filter driver does not use direct OID
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function. If a filter driver defines a 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function,
    it must provide the 
    <i>FilterDirectOidRequestComplete</i> function.</p>

<p>If the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a> function
    returns NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterDirectOidRequestComplete</i> function to complete the OID request.</p>

<p>If a filter driver forwarded a request that it received in the 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function,
    
    <i>FilterDirectOidRequestComplete</i> should pass the completion status up the driver stack by calling the
    
    <a href="https://msdn.microsoft.com/b6b4d4f4-63d5-496c-9082-f2e8d1a174ec">
    NdisFDirectOidRequestComplete</a> function. In this case, the filter driver must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a>, to free
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure, before it calls
    
    <b>NdisFDirectOidRequestComplete</b>.</p>

<p>A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFDirectOidRequestComplete</b> when NDIS calls 
    <i>FilterDirectOidRequestComplete</i> for such requests.</p>

<p>NDIS calls 
    <i>FilterDirectOidRequestComplete</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>FilterDirectOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>FilterDirectOidRequestComplete</i> function that is named "MyDirectOidRequestComplete", use the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
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
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b6b4d4f4-63d5-496c-9082-f2e8d1a174ec">
   NdisFDirectOidRequestComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_DIRECT_OID_REQUEST_COMPLETE callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>