---
UID: NF.wdfinterrupt.WDF_INTERRUPT_CONFIG_INIT
title: WDF_INTERRUPT_CONFIG_INIT
author: windows-driver-content
description: The WDF_INTERRUPT_CONFIG_INIT function initializes a WDF_INTERRUPT_CONFIG structure.
old-location: wdf\wdf_interrupt_config_init.htm
ms.assetid: e81ec3da-a863-467f-82ec-1fa7ee6401b1
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_INTERRUPT_CONFIG_INIT
req.alt-loc: wdfinterrupt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
ms.keywords: WDF_INTERRUPT_CONFIG_INIT
req.iface: 
req.product: Windows 10 or later.
---

# WDF_INTERRUPT_CONFIG_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_INTERRUPT_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.</p>


## -syntax

````
VOID WDF_INTERRUPT_CONFIG_INIT(
  _Out_    PWDF_INTERRUPT_CONFIG Configuration,
  _In_     PFN_WDF_INTERRUPT_ISR EvtInterruptIsr,
  _In_opt_ PFN_WDF_INTERRUPT_DPC EvtInterruptDpc
);
````


## -parameters
<dl>

### -param <i>Configuration</i> [out]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.</p>
</dd>

### -param <i>EvtInterruptIsr</i> [in]

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function.</p>
</dd>

### -param <i>EvtInterruptDpc</i> [in, optional]

<dd>
<p>A pointer to the driver's <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> callback function, or <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>WDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also sets the structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and stores the specified callback function pointers. Finally, it sets the <b>ReportInactiveOnPowerDown</b>  member of the specified <b>WDF_INTERRUPT_CONFIG</b> structure to <b>WdfDefault</b>.</p>

<p>For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.</p>

<p>For a code example that uses <b>WDF_INTERRUPT_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.</p>

<p>The <b>WDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also sets the structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and stores the specified callback function pointers. Finally, it sets the <b>ReportInactiveOnPowerDown</b>  member of the specified <b>WDF_INTERRUPT_CONFIG</b> structure to <b>WdfDefault</b>.</p>

<p>For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.</p>

<p>For a code example that uses <b>WDF_INTERRUPT_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>.</p>

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
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfinterrupt.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_CONFIG_INIT function%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>