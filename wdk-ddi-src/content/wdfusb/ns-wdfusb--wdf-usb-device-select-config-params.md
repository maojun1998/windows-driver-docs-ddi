---
UID: NS.wdfusb._WDF_USB_DEVICE_SELECT_CONFIG_PARAMS
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure specifies USB device configuration parameters.
old-location: wdf\wdf_usb_device_select_config_params.htm
ms.assetid: d48484eb-a7bf-4ca7-9d18-4c4c166db90c
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS
req.alt-loc: wdfusb.h
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
ms.keywords: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS, *PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS
req.iface: 
req.product: Windows 10 or later.
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</b> structure specifies USB device configuration parameters.</p>


## -syntax

````
typedef struct _WDF_USB_DEVICE_SELECT_CONFIG_PARAMS {
  ULONG                              Size;
  WdfUsbTargetDeviceSelectConfigType Type;
  union {
    struct {
      PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor;
      PUSB_INTERFACE_DESCRIPTOR     *InterfaceDescriptors;
      ULONG                         NumInterfaceDescriptors;
    } Descriptor;
    struct {
      PURB Urb;
    } Urb;
    struct {
      UCHAR           NumberConfiguredPipes;
      WDFUSBINTERFACE ConfiguredUsbInterface;
    } SingleInterface;
    struct {
      UCHAR                           NumberInterfaces;
      PWDF_USB_INTERFACE_SETTING_PAIR Pairs;
      UCHAR                           NumberOfConfiguredInterfaces;
    } MultiInterface;
  } Types;
} WDF_USB_DEVICE_SELECT_CONFIG_PARAMS, *PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The size, in bytes, of this structure. </p>
</dd>

### -field <b>Type</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550102">WdfUsbTargetDeviceSelectConfigType</a>-typed value that either specifies the type of configuration that is being selected or indicates that the current configuration is being deconfigured.</p>
</dd>

### -field <b>Types</b>

<dd>
<dl>

### -field <b>Descriptor</b>

<dd>
<dl>

### -field <b>ConfigurationDescriptor</b>

<dd>
<p>If the driver sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor</b>, this member contains a driver-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> structure that specifies a configuration descriptor. If this pointer is <b>NULL</b>, the framework uses the device's first configuration. For more information about selecting a USB configuration, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a>.</p>
</dd>

### -field <b>InterfaceDescriptors</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor</b>, this member contains a driver-supplied pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structures that represent the interfaces to select for the configuration.</p>
</dd>

### -field <b>NumInterfaceDescriptors</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor</b>, this member contains the number of elements that are in the interface array that <b>Types.Descriptor.InterfaceDescriptors</b> points to.</p>
</dd>
</dl>
</dd>

### -field <b>Urb</b>

<dd>
<dl>

### -field <b>Urb</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeUrb</b>, this member specifies a driver-initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure that the framework uses to configure the device. </p>
</dd>
</dl>
</dd>

### -field <b>SingleInterface</b>

<dd>
<dl>

### -field <b>NumberConfiguredPipes</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeSingleInterface</b>, the framework provides the number of pipes that are configured for the interface. </p>
</dd>

### -field <b>ConfiguredUsbInterface</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeSingleInterface</b>, the framework provides a handle to a USB interface object that represents the configured interface. </p>
</dd>
</dl>
</dd>

### -field <b>MultiInterface</b>

<dd>
<dl>

### -field <b>NumberInterfaces</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</b>, this member specifies the number of elements that are in the <b>Types.MultiInterface.Pairs</b> array.</p>
</dd>

### -field <b>Pairs</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</b>, this member specifies a pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553023">WDF_USB_INTERFACE_SETTING_PAIR</a> structures that identify the interfaces to select. </p>
</dd>

### -field <b>NumberOfConfiguredInterfaces</b>

<dd>
<p>If the driver sets <b>Type</b> to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</b> or <b>WdfUsbTargetDeviceSelectConfigTypeMultiInterface</b>, the framework provides the number if interfaces that are configured for the device.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</b> structure is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a>.</p>

<p>To initialize a <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</b> structure, use one of the following functions:</p><dl>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552992">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552997">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>
</p>
</dd>
</dl><p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552992">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552997">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>
</p>

<p>If the driver sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor</b>, it can change the USB device configuration. All other values use the current USB device configuration.</p>

## -requirements
<table>
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
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553023">WDF_USB_INTERFACE_SETTING_PAIR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550102">WdfUsbTargetDeviceSelectConfigType</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>