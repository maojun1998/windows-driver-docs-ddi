---
UID: NI.acpiioct.IOCTL_ACPI_ENUM_CHILDREN
title: IOCTL_ACPI_ENUM_CHILDREN
author: windows-driver-content
description: The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent.
old-location: acpi\ioctl_acpi_enum_children.htm
ms.assetid: 86d713e0-ec1e-4417-9ff7-8574bd040a6e
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: acpi
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_ACPI_ENUM_CHILDREN
req.alt-loc: Acpiioct.h
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
ms.keywords: UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
---

# IOCTL_ACPI_ENUM_CHILDREN IOCTL



## -description
<p>The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent. A driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a> and pass the following input and output parameters to build this request. </p>


## -ioctlparameters

### -input-buffer
<p>Set the <b>IoBuildDeviceIoControlRequest</b> input parameters as follows:</p>

<p><i>IoControlCode</i> is set to IOCTL_ACPI_ENUM_CHILDREN.</p>

<p><i>DeviceObject</i> is set to a pointer to the physical device object (PDO) of the device.</p>

<p><i>InputBuffer</i> is set to a pointer to a variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536110">ACPI_ENUM_CHILDREN_INPUT_BUFFER</a> structure.</p>

<p><i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.</p>

<p><i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.</p>

<p><i>InternalDeviceIoControl</i> is set to <b>FALSE</b>.</p>

<p><i>Event</i> is set to a pointer to a caller-allocated and initialized event object.</p>

### -input-buffer-length
<p><i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.</p>

<p><i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.</p>

### -output-buffer
<p>Set the <b>IoBuildDeviceIoControlRequest</b> output parameters as follows:</p>

<p><i>OutputBuffer</i> supplies a pointer to a variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure in which the ACPI driver returns the path and name of the enumerated child devices.</p>

<p><i>IoStatusBlock</i> is set to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure.</p>

<p>Set the <b>IoBuildDeviceIoControlRequest</b> output parameters as follows:</p>

<p><i>OutputBuffer</i> supplies a pointer to a variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure in which the ACPI driver returns the path and name of the enumerated child devices.</p>

<p><i>IoStatusBlock</i> is set to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure.</p>

<p>Set the <b>IoBuildDeviceIoControlRequest</b> output parameters as follows:</p>

<p><i>OutputBuffer</i> supplies a pointer to a variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure in which the ACPI driver returns the path and name of the enumerated child devices.</p>

<p><i>IoStatusBlock</i> is set to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure.</p>

### -output-buffer-length
<p><i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.</p>

<p><i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.</p>

<p><i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.</p>

<p><i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.</p>

<p>If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.</p>

<p>If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.</p>

<p>If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.</p>

<p>If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.</p>

<p>If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.</p>

<p>If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.</p>

<p>If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.</p>

<p>If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.</p>

<p>If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.</p>

## -remarks
<p>IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:</p>

<p></p><dl>
<dt><a id="ENUM_CHILDREN_IMMEDIATE_ONLY_"></a><a id="enum_children_immediate_only_"></a>ENUM_CHILDREN_IMMEDIATE_ONLY </dt>
<dd>
<p>Enumerates the device and enumerates the immediate child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL_"></a><a id="enum_children_multilevel_"></a>ENUM_CHILDREN_MULTILEVEL </dt>
<dd>
<p>Enumerates the device and recursively enumerates all child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL____ENUM_CHILDREN_NAME_IS_FILTER_"></a><a id="enum_children_multilevel____enum_children_name_is_filter_"></a>ENUM_CHILDREN_MULTILEVEL || ENUM_CHILDREN_NAME_IS_FILTER </dt>
<dd>
<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>
</dd>
</dl><p>Enumerates the device and enumerates the immediate child devices of the device.</p>

<p>Enumerates the device and recursively enumerates all child devices of the device.</p>

<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>

<p>If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. </p>

<p>A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. </p>

<p>For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:</p>

<p></p><dl>
<dt><a id="ENUM_CHILDREN_IMMEDIATE_ONLY_"></a><a id="enum_children_immediate_only_"></a>ENUM_CHILDREN_IMMEDIATE_ONLY </dt>
<dd>
<p>Enumerates the device and enumerates the immediate child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL_"></a><a id="enum_children_multilevel_"></a>ENUM_CHILDREN_MULTILEVEL </dt>
<dd>
<p>Enumerates the device and recursively enumerates all child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL____ENUM_CHILDREN_NAME_IS_FILTER_"></a><a id="enum_children_multilevel____enum_children_name_is_filter_"></a>ENUM_CHILDREN_MULTILEVEL || ENUM_CHILDREN_NAME_IS_FILTER </dt>
<dd>
<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>
</dd>
</dl><p>Enumerates the device and enumerates the immediate child devices of the device.</p>

<p>Enumerates the device and recursively enumerates all child devices of the device.</p>

<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>

<p>If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. </p>

<p>A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. </p>

<p>For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:</p>

<p></p><dl>
<dt><a id="ENUM_CHILDREN_IMMEDIATE_ONLY_"></a><a id="enum_children_immediate_only_"></a>ENUM_CHILDREN_IMMEDIATE_ONLY </dt>
<dd>
<p>Enumerates the device and enumerates the immediate child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL_"></a><a id="enum_children_multilevel_"></a>ENUM_CHILDREN_MULTILEVEL </dt>
<dd>
<p>Enumerates the device and recursively enumerates all child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL____ENUM_CHILDREN_NAME_IS_FILTER_"></a><a id="enum_children_multilevel____enum_children_name_is_filter_"></a>ENUM_CHILDREN_MULTILEVEL || ENUM_CHILDREN_NAME_IS_FILTER </dt>
<dd>
<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>
</dd>
</dl><p>Enumerates the device and enumerates the immediate child devices of the device.</p>

<p>Enumerates the device and recursively enumerates all child devices of the device.</p>

<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>

<p>If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. </p>

<p>A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. </p>

<p>For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:</p>

<p></p><dl>
<dt><a id="ENUM_CHILDREN_IMMEDIATE_ONLY_"></a><a id="enum_children_immediate_only_"></a>ENUM_CHILDREN_IMMEDIATE_ONLY </dt>
<dd>
<p>Enumerates the device and enumerates the immediate child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL_"></a><a id="enum_children_multilevel_"></a>ENUM_CHILDREN_MULTILEVEL </dt>
<dd>
<p>Enumerates the device and recursively enumerates all child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL____ENUM_CHILDREN_NAME_IS_FILTER_"></a><a id="enum_children_multilevel____enum_children_name_is_filter_"></a>ENUM_CHILDREN_MULTILEVEL || ENUM_CHILDREN_NAME_IS_FILTER </dt>
<dd>
<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>
</dd>
</dl><p>Enumerates the device and enumerates the immediate child devices of the device.</p>

<p>Enumerates the device and recursively enumerates all child devices of the device.</p>

<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>

<p>If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. </p>

<p>A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. </p>

<p>For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:</p>

<p></p><dl>
<dt><a id="ENUM_CHILDREN_IMMEDIATE_ONLY_"></a><a id="enum_children_immediate_only_"></a>ENUM_CHILDREN_IMMEDIATE_ONLY </dt>
<dd>
<p>Enumerates the device and enumerates the immediate child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL_"></a><a id="enum_children_multilevel_"></a>ENUM_CHILDREN_MULTILEVEL </dt>
<dd>
<p>Enumerates the device and recursively enumerates all child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL____ENUM_CHILDREN_NAME_IS_FILTER_"></a><a id="enum_children_multilevel____enum_children_name_is_filter_"></a>ENUM_CHILDREN_MULTILEVEL || ENUM_CHILDREN_NAME_IS_FILTER </dt>
<dd>
<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>
</dd>
</dl><p>Enumerates the device and enumerates the immediate child devices of the device.</p>

<p>Enumerates the device and recursively enumerates all child devices of the device.</p>

<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>

<p>If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. </p>

<p>A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. </p>

<p>For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:</p>

<p></p><dl>
<dt><a id="ENUM_CHILDREN_IMMEDIATE_ONLY_"></a><a id="enum_children_immediate_only_"></a>ENUM_CHILDREN_IMMEDIATE_ONLY </dt>
<dd>
<p>Enumerates the device and enumerates the immediate child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL_"></a><a id="enum_children_multilevel_"></a>ENUM_CHILDREN_MULTILEVEL </dt>
<dd>
<p>Enumerates the device and recursively enumerates all child devices of the device.</p>
</dd>
<dt><a id="ENUM_CHILDREN_MULTILEVEL____ENUM_CHILDREN_NAME_IS_FILTER_"></a><a id="enum_children_multilevel____enum_children_name_is_filter_"></a>ENUM_CHILDREN_MULTILEVEL || ENUM_CHILDREN_NAME_IS_FILTER </dt>
<dd>
<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>
</dd>
</dl><p>Enumerates the device and enumerates the immediate child devices of the device.</p>

<p>Enumerates the device and recursively enumerates all child devices of the device.</p>

<p>A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.</p>

<p>If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. </p>

<p>A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. </p>

<p>For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.</p>

<p>IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows Vista and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536110">ACPI_ENUM_CHILDREN_INPUT_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20IOCTL_ACPI_ENUM_CHILDREN control code%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>