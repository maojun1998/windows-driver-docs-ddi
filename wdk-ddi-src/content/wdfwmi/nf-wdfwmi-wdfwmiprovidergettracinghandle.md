---
UID: NF.wdfwmi.WdfWmiProviderGetTracingHandle
title: WdfWmiProviderGetTracingHandle
author: windows-driver-content
description: The WdfWmiProviderGetTracingHandle method returns a handle to the event logger of a WPP software tracing session.
old-location: wdf\wdfwmiprovidergettracinghandle.htm
ms.assetid: 44ab1cf3-abd3-4100-a6ad-51f2322881b1
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfWmiProviderGetTracingHandle
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
ms.keywords: WdfWmiProviderGetTracingHandle
req.iface: 
req.product: Windows 10 or later.
---

# WdfWmiProviderGetTracingHandle function



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>The <b>WdfWmiProviderGetTracingHandle</b> method returns a handle to the event logger of a <a href="NULL">WPP software tracing</a> session. </p>


## -syntax

````
ULONGLONG WdfWmiProviderGetTracingHandle(
  _In_ WDFWMIPROVIDER WmiProvider
);
````


## -parameters
<dl>

### -param <i>WmiProvider</i> [in]

<dd>
<p>A handle to a WMI provider object that the driver obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551187">WdfWmiInstanceGetProvider</a>.</p>
</dd>
</dl>

## -returns
<p><b>WdfWmiProviderGetTracingHandle</b> returns a handle to the event tracing logger.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>If a driver sets the <b>WdfWmiProviderTracing</b> flag in the <b>Flags</b> member of the WMI provider object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure, it can call <b>WdfWmiProviderGetTracingHandle</b> to obtain a tracing handle after a provider instance has been registered. The driver can use the tracing handle as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565836">WmiTraceMessage</a> routine.</p>

<p>For more information about the <b>WdfWmiProviderGetTracingHandle</b> method, see <a href="wdf.supporting_wmi_data_blocks_and_events_in_your_driver#supporting_wmi_event_tracing#supporting_wmi_event_tracing">Supporting WMI Event Tracing</a>. For more information about WMI, see <a href="wdf.supporting_wmi_in_kmdf_drivers">Supporting WMI in Framework-Based Drivers</a>.</p>

<p>The following code example obtains a handle to a WPP tracing session's event logger.</p>

<p>If a driver sets the <b>WdfWmiProviderTracing</b> flag in the <b>Flags</b> member of the WMI provider object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a> structure, it can call <b>WdfWmiProviderGetTracingHandle</b> to obtain a tracing handle after a provider instance has been registered. The driver can use the tracing handle as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565836">WmiTraceMessage</a> routine.</p>

<p>For more information about the <b>WdfWmiProviderGetTracingHandle</b> method, see <a href="wdf.supporting_wmi_data_blocks_and_events_in_your_driver#supporting_wmi_event_tracing#supporting_wmi_event_tracing">Supporting WMI Event Tracing</a>. For more information about WMI, see <a href="wdf.supporting_wmi_in_kmdf_drivers">Supporting WMI in Framework-Based Drivers</a>.</p>

<p>The following code example obtains a handle to a WPP tracing session's event logger.</p>

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
<dt>Wdfwmi.h (include Wdf.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553067">WDF_WMI_PROVIDER_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551187">WdfWmiInstanceGetProvider</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiProviderGetTracingHandle method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>