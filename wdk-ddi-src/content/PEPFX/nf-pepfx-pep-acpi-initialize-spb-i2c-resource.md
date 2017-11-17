---
UID: NF.pepfx.PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
title: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
author: windows-driver-content
description: The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_spb_i2c_resource.htm
ms.assetid: 5F1606D8-1E6F-494F-AE70-07A1EC1FEA47
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE
req.iface: 
---

# PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function



## -description
<p>The <b>PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://msdn.microsoft.com/library/windows/hardware/mt186694">PEP_ACPI_SPB_I2C_RESOURCE</a> structure.</p>


## -syntax

````
FORCEINLINE VOID PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE(
  _In_  USHORT             SlaveAddress,
  _In_  BOOLEAN            DeviceInitiated,
  _In_  ULONG              ConnectionSpeed,
  _In_  BOOLEAN            AddressingMode,
  _In_  PUNICODE_STRING    ResourceSource,
  _In_  UCHAR              ResourceSourceIndex,
  _In_  BOOLEAN            ResourceUsage,
  _In_  BOOLEAN            SharedMode,
  _In_  PCHAR              VendorData,
  _In_  USHORT             VendorDataLength,
  _Out_ PPEP_ACPI_RESOURCE Resource
);
````


## -parameters
<dl>

### -param <i>SlaveAddress</i> [in]

<dd>
<p>The I2C bus address for this connection.</p>
</dd>

### -param <i>DeviceInitiated</i> [in]

<dd>
<p>If true, indicates that communication over this connection is initiated by the device.</p>
</dd>

### -param <i>ConnectionSpeed</i> [in]

<dd>
<p>The maximum speed, in hertz, supported by this connection.</p>
</dd>

### -param <i>AddressingMode</i> [in]

<dd>
<p>Indicates that this device is in addressing mode.</p>
</dd>

### -param <i>ResourceSource</i> [in]

<dd>
<p>The name of the serial bus controller device to which this
connection descriptor applies. The name can be a fully
qualified path, a relative path, or a simple name segment
that utilizes the namespace search rules.</p>
</dd>

### -param <i>ResourceSourceIndex</i> [in]

<dd>
<p>This parameter should always be set to zero.</p>
</dd>

### -param <i>ResourceUsage</i> [in]

<dd>
<p>Indicates if the resource is in use.</p>
</dd>

### -param <i>SharedMode</i> [in]

<dd>
<p>Indicates if the resource is shared.</p>
</dd>

### -param <i>VendorData</i> [in]

<dd>
<p>A pointer to optional data that is specific to the serial bus connection type.</p>
</dd>

### -param <i>VendorDataLength</i> [in]

<dd>
<p>The length of the buffer pointed to by the <i>VendorData</i> parameter.</p>
</dd>

### -param <i>Resource</i> [out]

<dd>
<p>A pointer to the resource. The structure behind the pointer is of type <a href="https://msdn.microsoft.com/library/windows/hardware/mt186694">PEP_ACPI_SPB_I2C_RESOURCE</a>.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt186694">PEP_ACPI_SPB_I2C_RESOURCE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>