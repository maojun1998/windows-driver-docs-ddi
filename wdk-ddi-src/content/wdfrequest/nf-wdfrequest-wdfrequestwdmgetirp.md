---
UID: NF.wdfrequest.WdfRequestWdmGetIrp
title: WdfRequestWdmGetIrp
author: windows-driver-content
description: The WdfRequestWdmGetIrp method returns the WDM IRP structure that is associated with a specified framework request object.
old-location: wdf\wdfrequestwdmgetirp.htm
ms.assetid: 414950c6-b082-4ea9-bba4-f3d12b4d2a9e
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfRequestWdmGetIrp
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: WdfRequestWdmGetIrp
req.iface: 
req.product: Windows 10 or later.
---

# WdfRequestWdmGetIrp function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfRequestWdmGetIrp</b> method returns the WDM <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure that is associated with a specified framework request object.</p>


## -syntax

````
PIRP WdfRequestWdmGetIrp(
  _In_ WDFREQUEST Request
);
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object.</p>
</dd>
</dl>

## -returns
<p><b>WdfRequestWdmGetIrp</b> returns a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>The driver must not access a request's IRP structure after <a href="wdf.completing_i_o_requests">completing the I/O request</a>.</p>

<p>For more information about <b>WdfRequestWdmGetIrp</b>, see <a href="wdf.obtaining_information_about_an_i_o_request">Obtaining Information About an I/O Request</a>.</p>

<p>The following code example is part of an <a href="https://msdn.microsoft.com/3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce">EvtIoDeviceControl</a> callback function that obtains the WDM IRP that is associated with an I/O request and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a> to obtain the next-lower driver's I/O stack location.</p>

<p>The driver must not access a request's IRP structure after <a href="wdf.completing_i_o_requests">completing the I/O request</a>.</p>

<p>For more information about <b>WdfRequestWdmGetIrp</b>, see <a href="wdf.obtaining_information_about_an_i_o_request">Obtaining Information About an I/O Request</a>.</p>

<p>The following code example is part of an <a href="https://msdn.microsoft.com/3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce">EvtIoDeviceControl</a> callback function that obtains the WDM IRP that is associated with an I/O request and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a> to obtain the next-lower driver's I/O stack location.</p>

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
<dt>Wdfrequest.h (include Wdf.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547261">InvalidReqAccess</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547267">InvalidReqAccessLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestWdmGetIrp method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>