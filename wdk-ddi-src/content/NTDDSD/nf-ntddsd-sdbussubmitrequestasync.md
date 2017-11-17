---
UID: NF.ntddsd.SdBusSubmitRequestAsync
title: SdBusSubmitRequestAsync
author: windows-driver-content
description: The SdBusSubmitRequestAsync routine sends an asynchronous Secure Digital (SD) request to the bus driver interface.
old-location: sd\sdbussubmitrequestasync.htm
ms.assetid: c4425ba5-adf7-4734-a400-1a233a441047
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: SD
req.header: ntddsd.h
req.include-header: Ntddsd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SdBusSubmitRequestAsync
req.alt-loc: ntddsd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: SdBusSubmitRequestAsync
req.iface: 
---

# SdBusSubmitRequestAsync function



## -description
<p>The <b>SdBusSubmitRequestAsync</b> routine sends an asynchronous Secure Digital (SD) request to the bus driver interface.</p>


## -syntax

````
NTSTATUS SdBusSubmitRequestAsync(
  _In_ PVOID                  InterfaceContext,
  _In_ PSDBUS_REQUEST_PACKET  Packet,
  _In_ PIRP                   Irp,
  _In_ PIO_COMPLETION_ROUTINE CompletionRoutine,
  _In_ PVOID                  UserContext
);
````


## -parameters
<dl>

### -param <i>InterfaceContext</i> [in]

<dd>
<p>Contains the context information returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.</p>
</dd>

### -param <i>Packet</i> [in]

<dd>
<p>Pointer to a caller-supplied structure of type <a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a> that describes the request.</p>
</dd>

### -param <i>Irp</i> [in]

<dd>
<p>Points to a caller-supplied IRP that the SD library uses to transmit the request packet. The <b>SdBusSubmitRequestAsync</b> routine stores the packet in the next stack location of the IRP, which allows the caller to reuse IRPs created by a driver higher in the stack.</p>
</dd>

### -param <i>CompletionRoutine</i> [in]

<dd>
<p>Pointer to a completion routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> that <b>SdBusSubmitRequestAsync</b> registers for the IRP specified in the <i>Irp </i>parameter.</p>
</dd>

### -param <i>UserContext</i> [in]

<dd>
<p>Pointer to context data that the system passes to the completion routine registered for the IRP specified by the <i>Irp </i>parameter.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS or STATUS_PENDING if the operation succeeds, or the appropriate error message if the operation fails.</p>

## -remarks
<p>Callers of <b>SdBusSubmitRequestAsync</b> must be running at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a> must be running at IRQL &lt; DISPATCH_LEVEL.</p>

<p>This request is handled asynchronously and might return STATUS_PENDING. </p>

<p>Callers of <b>SdBusSubmitRequestAsync</b> must be running at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a> must be running at IRQL &lt; DISPATCH_LEVEL.</p>

<p>This request is handled asynchronously and might return STATUS_PENDING. </p>

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
<dt>Ntddsd.h (include Ntddsd.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537909">SdBusSubmitRequest</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SdBusSubmitRequestAsync function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>