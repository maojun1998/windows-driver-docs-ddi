---
UID: NS.ntddndis._NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
title: NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure specifies an array of profile properties for the Hyper-V extensible switch. Each element in the array is formatted as an NDIS_SWITCH_PROPERTY_ENUM_INFO structure.
old-location: netvista\ndis_switch_property_enum_parameters.htm
ms.assetid: f133f6cc-6e09-4eb8-b6fe-50d207391621
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, *PNDIS_SWITCH_PROPERTY_ENUM_PARAMETERS
req.iface: 
---

# NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure



## -description
<p>The <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure specifies an array of profile properties for the Hyper-V extensible switch. Each element in the array is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598250">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> structure.</p>


## -syntax

````
typedef struct _NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS {
  NDIS_OBJECT_HEADER                       Header;
  ULONG                                    Flags;
  NDIS_SWITCH_PROPERTY_TYPE                PropertyType;
  NDIS_SWITCH_OBJECT_ID                    PropertyId;
  NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION SerializationVersion;
  ULONG                                    FirstPropertyOffset;
  ULONG                                    NumProperties;
} NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS, *PNDIS_SWITCH_PROPERTY_ENUM_PARAMETERS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.</p>
<p>The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:</p>
<p></p>
<dl>

### -field <a id="NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_REVISION_1"></a><a id="ndis_switch_property_enum_parameters_revision_1"></a>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_REVISION_1

<dd>
<p>Original version for NDIS 6.30 and later.</p>
<p>Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_REVISION_1.</p>
</dd>
</dl>
</dd>

### -field <b>Flags</b>

<dd>
<p>A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.</p>
</dd>

### -field <b>PropertyType</b>

<dd>
<p> An <a href="https://msdn.microsoft.com/library/windows/hardware/hh598257">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration value that specifies the extensible switch property type. When an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a> is issued, the extensible switch extension returns extensible switch properties that match this property type.</p>
</dd>

### -field <b>PropertyId</b>

<dd>
<p>A GUID value that identifies the extensible switch property.

</p>
</dd>

### -field <b>SerializationVersion</b>

<dd>
<p>An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized extensible switch property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.</p>
<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>
</dd>

### -field <b>FirstPropertyOffset</b>

<dd>
<p>A USHORT value that specifies the offset, in bytes, to the first <a href="https://msdn.microsoft.com/library/windows/hardware/hh598250">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> element that follows the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure. The offset is measured from the start of the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure up to the beginning of the first element in the array.</p>
<div class="alert"><b>Note</b>  If the value of <b>NumProperties</b> is zero, this member is ignored. </div>
<div> </div>
</dd>

### -field <b>NumProperties</b>

<dd>
<p>A ULONG value that specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598250">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> elements that follow the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure. </p>
</dd>
</dl>

## -remarks
<p>The <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a>. An array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598250">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> structures follows the <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure in the information buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.</p>

<p>Extensible switch extensions can access the first <a href="https://msdn.microsoft.com/library/windows/hardware/hh598250">NDIS_SWITCH_PROPERTY_ENUM_INFO</a> structure that is specified by the  <b>NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS</b> structure by using the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598254">NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS_GET_FIRST_INFO</a> macro.</p>

<p>For more information about extensible switch policies, see <a href="NULL">Hyper-V Extensible Switch Policies</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598250">NDIS_SWITCH_PROPERTY_ENUM_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598282">OID_SWITCH_PROPERTY_ENUM</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PROPERTY_ENUM_PARAMETERS structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>