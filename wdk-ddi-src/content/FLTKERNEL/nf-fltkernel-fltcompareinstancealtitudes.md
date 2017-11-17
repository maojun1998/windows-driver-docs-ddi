---
UID: NF.fltkernel.FltCompareInstanceAltitudes
title: FltCompareInstanceAltitudes
author: windows-driver-content
description: FltCompareInstanceAltitudes compares the altitudes of two minifilter driver instances.
old-location: ifsk\fltcompareinstancealtitudes.htm
ms.assetid: aed86b34-4a9e-4c39-be0f-fa57829fa926
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltCompareInstanceAltitudes
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: FltCompareInstanceAltitudes
req.iface: 
---

# FltCompareInstanceAltitudes function



## -description
<p><b>FltCompareInstanceAltitudes</b> compares the altitudes of two minifilter driver instances. </p>


## -syntax

````
LONG FltCompareInstanceAltitudes(
  _In_ PFLT_INSTANCE Instance1,
  _In_ PFLT_INSTANCE Instance2
);
````


## -parameters
<dl>

### -param <i>Instance1</i> [in]

<dd>
<p>Pointer to the first instance. </p>
</dd>

### -param <i>Instance2</i> [in]

<dd>
<p>Pointer to the second instance. </p>
</dd>
</dl>

## -returns
<p><b>FltCompareInstanceAltitudes</b> returns a signed value that gives the results of the comparison as follows: </p><dl>
<dt><b>Zero</b></dt>
</dl><p><i>Instance1</i> is attached at the same altitude as <i>Instance2</i>. This can only occur if <i>Instance1</i> and <i>Instance2</i> are attached to different volumes or if <i>Instance1</i> and <i>Instance2</i> are pointers to the same instance. </p><dl>
<dt><b>Less than zero</b></dt>
</dl><p><i>Instance1</i> is attached at a lower altitude than <i>Instance2</i>. </p><dl>
<dt><b>Greater than zero</b></dt>
</dl><p><i>Instance1</i> is attached at a higher altitude than <i>Instance2</i>. </p>

<p> </p>

## -remarks
<p>The minifilter driver instances that <i>Instance1</i> and <i>Instance2</i> point to can be instances of the same minifilter driver or different minifilter drivers. However, they must be attached to the same volume if the result returned by <b>FltCompareInstanceAltitudes</b> is to be meaningful. </p>

<p>The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. </p>

<p>Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string that consists of one or more decimal digits from 0 through 9; the string can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. </p>

<p>The string "03333" represents a higher altitude than "100.123456" (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. </p>

<p>To attach a minifilter driver instance to a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541772">FltAttachVolume</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>. </p>

<p>To detach a minifilter driver instance from a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>. </p>

<p>The minifilter driver instances that <i>Instance1</i> and <i>Instance2</i> point to can be instances of the same minifilter driver or different minifilter drivers. However, they must be attached to the same volume if the result returned by <b>FltCompareInstanceAltitudes</b> is to be meaningful. </p>

<p>The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. </p>

<p>Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string that consists of one or more decimal digits from 0 through 9; the string can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. </p>

<p>The string "03333" represents a higher altitude than "100.123456" (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. </p>

<p>To attach a minifilter driver instance to a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541772">FltAttachVolume</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>. </p>

<p>To detach a minifilter driver instance from a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541772">FltAttachVolume</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541889">FltCompareInstanceAltitudes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCompareInstanceAltitudes function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>