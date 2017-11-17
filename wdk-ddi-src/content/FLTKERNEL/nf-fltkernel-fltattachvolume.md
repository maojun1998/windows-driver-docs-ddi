---
UID: NF.fltkernel.FltAttachVolume
title: FltAttachVolume
author: windows-driver-content
description: FltAttachVolume creates a new minifilter driver instance and attaches it to the given volume.
old-location: ifsk\fltattachvolume.htm
ms.assetid: da85c8d6-a74c-4a87-88b3-fb6dc01dd0f9
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
req.alt-api: FltAttachVolume
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
req.irql: <= APC_LEVEL
ms.keywords: FltAttachVolume
req.iface: 
---

# FltAttachVolume function



## -description
<p><b>FltAttachVolume</b> creates a new minifilter driver instance and attaches it to the given volume. </p>


## -syntax

````
NTSTATUS FltAttachVolume(
  _Inout_  PFLT_FILTER      Filter,
  _Inout_  PFLT_VOLUME      Volume,
  _In_opt_ PCUNICODE_STRING InstanceName,
  _Out_    PFLT_INSTANCE    *RetInstance
);
````


## -parameters
<dl>

### -param <i>Filter</i> [in, out]

<dd>
<p>Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param <i>Volume</i> [in, out]

<dd>
<p>Opaque volume pointer for the volume that the minifilter driver instance is to be attached to. This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param <i>InstanceName</i> [in, optional]

<dd>
<p>Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure containing the instance name for the new instance. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, <b>FltAttachVolume</b> attempts to read the minifilter driver's default instance name from the registry. (For more information about this parameter, see the following Remarks section.) </p>
</dd>

### -param <i>RetInstance</i> [out]

<dd>
<p>Pointer to a caller-allocated variable that receives an opaque instance pointer for the newly created instance. This parameter is optional and can be <b>NULL</b>. </p>
</dd>
</dl>

## -returns
<p><b>FltAttachVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: </p><dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl><p>The specified <i>Filter</i> or <i>Volume</i> is being torn down. This is an error code. </p><dl>
<dt><b>STATUS_FLT_FILTER_NOT_READY</b></dt>
</dl><p>The minifilter driver has not started filtering. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544569">FltStartFiltering</a>. This is an error code. </p><dl>
<dt><b>STATUS_FLT_INSTANCE_NAME_COLLISION</b></dt>
</dl><p>An instance already exists with this name on the volume specified. </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p><b>FltAttachVolume</b> encountered a pool allocation failure. This is an error code. </p><dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl><p>Another instance was already attached at the altitude specified in the instance attributes that were read from the registry. This is an error code. </p>

<p> </p>

## -remarks
<p>If the caller specifies a non-<b>NULL</b> value for <i>InstanceName</i>, <b>FltAttachVolume</b> reads any instance attributes specified by the minifilter driver that are stored in the registry under HKLM\CurrentControlSet\Services\<i>ServiceName</i>\Instances\InstanceName, where <i>ServiceName</i> is the minifilter driver's service name. This service name is specified in the <a href="devinst.inf_addservice_directive">AddService directive</a> in the <a href="devinst.inf_defaultinstall_services_section">DefaultInstall.Services section</a> of the minifilter driver's INF file. (For more information about filter driver INF files, see <a href="ifsk.installing_a_file_system_filter_driver">Installing a File System Filter Driver</a>.) </p>

<p>If the caller does not specify a value for <i>InstanceName</i>, <b>FltAttachVolume</b> uses the name stored in the registry under HKLM\CurrentControlSet\Services\<i>ServiceName</i>\Instances\DefaultInstance for the <i>InstanceName</i> portion of the registry path. </p>

<p>The instance name specified in the <i>InstanceName</i> parameter is required to be unique across the system. </p>

<p><b>FltAttachVolume</b> returns an opaque instance pointer for the new instance in <i>*RetInstance</i>. This pointer value uniquely identifies the minifilter driver instance and remains constant as long as the instance is attached to the volume. </p>

<p><b>FltAttachVolume</b> adds a rundown reference to the opaque instance pointer returned in <i>*RetInstance</i>. When this pointer is no longer needed, the caller must release it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>. Thus every successful call to <b>FltAttachVolume</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. </p>

<p>To attach a minifilter driver instance to a volume at a given altitude, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>. </p>

<p>To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541889">FltCompareInstanceAltitudes</a>. </p>

<p>To detach a minifilter driver instance from a volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>. </p>

<p>If the caller specifies a non-<b>NULL</b> value for <i>InstanceName</i>, <b>FltAttachVolume</b> reads any instance attributes specified by the minifilter driver that are stored in the registry under HKLM\CurrentControlSet\Services\<i>ServiceName</i>\Instances\InstanceName, where <i>ServiceName</i> is the minifilter driver's service name. This service name is specified in the <a href="devinst.inf_addservice_directive">AddService directive</a> in the <a href="devinst.inf_defaultinstall_services_section">DefaultInstall.Services section</a> of the minifilter driver's INF file. (For more information about filter driver INF files, see <a href="ifsk.installing_a_file_system_filter_driver">Installing a File System Filter Driver</a>.) </p>

<p>If the caller does not specify a value for <i>InstanceName</i>, <b>FltAttachVolume</b> uses the name stored in the registry under HKLM\CurrentControlSet\Services\<i>ServiceName</i>\Instances\DefaultInstance for the <i>InstanceName</i> portion of the registry path. </p>

<p>The instance name specified in the <i>InstanceName</i> parameter is required to be unique across the system. </p>

<p><b>FltAttachVolume</b> returns an opaque instance pointer for the new instance in <i>*RetInstance</i>. This pointer value uniquely identifies the minifilter driver instance and remains constant as long as the instance is attached to the volume. </p>

<p><b>FltAttachVolume</b> adds a rundown reference to the opaque instance pointer returned in <i>*RetInstance</i>. When this pointer is no longer needed, the caller must release it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>. Thus every successful call to <b>FltAttachVolume</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. </p>

<p>To attach a minifilter driver instance to a volume at a given altitude, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>. </p>

<p>To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541889">FltCompareInstanceAltitudes</a>. </p>

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
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541775">FltAttachVolumeAtAltitude</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541889">FltCompareInstanceAltitudes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543239">FltGetVolumeInstanceFromName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544569">FltStartFiltering</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAttachVolume function%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>