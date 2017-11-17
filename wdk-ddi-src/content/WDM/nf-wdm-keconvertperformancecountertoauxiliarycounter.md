---
UID: NF.wdm.KeConvertPerformanceCounterToAuxiliaryCounter
title: KeConvertPerformanceCounterToAuxiliaryCounter
author: windows-driver-content
description: The KeConvertPerformanceCounterToAuxiliaryCounter routine converts the specified performance counter value into an auxiliary counter value.
old-location: kernel\keconvertperformancecountertoauxiliarycounter.htm
ms.assetid: 69F7C73E-C609-4080-8CB8-2F4D9A8C695B
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeConvertPerformanceCounterToAuxiliaryCounter
req.alt-loc: Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Hal.dll
req.irql: Any level
ms.keywords: KeConvertPerformanceCounterToAuxiliaryCounter
req.iface: 
req.product: Windows 10 or later.
---

# KeConvertPerformanceCounterToAuxiliaryCounter function



## -description
<p>The  <b>KeConvertPerformanceCounterToAuxiliaryCounter</b> routine converts the specified performance counter value into an auxiliary counter value.</p>


## -syntax

````
NTSTATUS KeConvertPerformanceCounterToAuxiliaryCounter(
  _In_      ULONG64  PerformanceCounterValue,
  _Out_     PULONG64 AuxiliaryCounterValue,
  _Out_opt_ PULONG64 ConversionError
);
````


## -parameters
<dl>

### -param <i>PerformanceCounterValue</i> [in]

<dd>
<p>The performance counter value to convert.</p>
</dd>

### -param <i>AuxiliaryCounterValue</i> [out]

<dd>
<p>A pointer to the variable that contains the converted auxiliary counter value.</p>
</dd>

### -param <i>ConversionError</i> [out, optional]

<dd>
<p>A pointer to a variable that contains the estimated conversion error in units of nanosecond.</p>
</dd>
</dl>

## -returns
<p><b>KeConvertPerformanceCounterToAuxiliaryCounter</b> can return one of the following:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The conversion succeeded.</p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>Auxiliary counter is not supported.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl><p>The <i>PerformanceCounterValue</i> value is not valid. For example, the value is earlier than the last system boot/recovery, or is out of the +/- 10s range compared to the current performance counter value.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL </b></dt>
</dl><p>The routine cannot convert the specified value with acceptable accuracy.</p>

<p> </p>

## -remarks
<p>Make sure that the specified performance counter value is:</p>

<p>The <i>ConversionError</i> value is the difference, in nanoseconds, between the expected calculated value and the actual calculated value for the auxiliary counter.
If the <i>ConversionError</i> value is greater than the expected value (determined by you), then call the routine again. </p>

<p>Make sure that the specified performance counter value is:</p>

<p>The <i>ConversionError</i> value is the difference, in nanoseconds, between the expected calculated value and the actual calculated value for the auxiliary counter.
If the <i>ConversionError</i> value is greater than the expected value (determined by you), then call the routine again. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Hal.dll</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt146560">KeConvertAuxiliaryCounterToPerformanceCounter</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeConvertPerformanceCounterToAuxiliaryCounter routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>