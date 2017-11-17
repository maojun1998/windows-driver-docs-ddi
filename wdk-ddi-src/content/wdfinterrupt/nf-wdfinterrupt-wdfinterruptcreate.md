---
UID: NF.wdfinterrupt.WdfInterruptCreate
title: WdfInterruptCreate
author: windows-driver-content
description: The WdfInterruptCreate method creates a framework interrupt object.
old-location: wdf\wdfinterruptcreate.htm
ms.assetid: 6279f9ed-f271-45e6-92ef-2a919f3584ed
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
req.alt-api: WdfInterruptCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
ms.keywords: WdfInterruptCreate
req.iface: 
req.product: Windows 10 or later.
---

# WdfInterruptCreate function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfInterruptCreate</b> method creates a framework interrupt object.</p>


## -syntax

````
NTSTATUS WdfInterruptCreate(
  _In_     WDFDEVICE              Device,
  _In_     PWDF_INTERRUPT_CONFIG  Configuration,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    WDFINTERRUPT           *Interrupt
);
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>

### -param <i>Configuration</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure that was initialized by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552348">WDF_INTERRUPT_CONFIG_INIT</a>.</p>
</dd>

### -param <i>Attributes</i> [in, optional]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework interrupt object.  (See Remarks for additional information.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.</p>
</dd>

### -param <i>Interrupt</i> [out]

<dd>
<p>A pointer to a location that receives a handle to the new interrupt object.</p>
</dd>
</dl>

## -returns
<p><b>WdfInterruptCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values.</p><dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl><p>The size of the WDF_INTERRUPT_CONFIG structure is incorrect.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An invalid parameter was specified.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl><p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a> was called after the device was started.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a> also returns this value if the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540880">EVT_WDF_DEVICE_PREPARE_HARDWARE</a> callback routine calls <b>WdfInterruptCreate</b> with   the <b>InterruptRaw</b> and <b>InterruptTranslated</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure set to <b>NULL</b>.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>There was insufficient memory.</p><dl>
<dt><b>STATUS_WDF_PARENT_ASSIGNMENT_NOT_ALLOWED</b></dt>
</dl><p>In KMDF version 1.9 or earlier, the driver specified a non-<b>NULL</b> value for the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure.</p>

<p>In KMDF version 1.11 or later, the driver specified a value other than a framework device or queue for the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure.</p><dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl><p>The <b>AutomaticSerialization</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure is set to <b>TRUE</b> and either:</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>.</p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The driver requested passive-level interrupt handling on a platform earlier than Windows 8.</p>

<p> </p>

<p>For a list of other return values that the <b>WdfInterruptCreate</b> method might return, see <a href="wdf.framework_object_creation_errors">Framework Object Creation Errors</a>.</p>

<p>This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>Drivers typically call the  <b>WdfInterruptCreate</b> method from an <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. Starting in KMDF version 1.11 and UMDF version 2.0, drivers can call <b>WdfInterruptCreate</b> from <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDriverDeviceAdd</i>, the <b>InterruptRaw</b>  and <b>InterruptTranslated</b>  members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure
must be NULL. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDevicePrepareHardware</i>, these members must both be valid.</p>

<p>If you are creating a wake-capable interrupt object, as described in <a href="wdf.using_an_interrupt_to_wake_a_device">Using an Interrupt to Wake a Device</a>, you must call <b>WdfInterruptCreate</b> from <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>.</p>

<p> Your driver must call <b>WdfInterruptCreate</b> once for each interrupt vector that its device requires. If the device supports message-signaled interrupts (MSI), the driver must create an interrupt object for each message that the device can support.</p>

<p>After the PnP manager assigns system resources to the device, the framework stores information about the device's assigned interrupt resources in the interrupt objects that the driver has created. (Drivers that <a href="wdf.using_kernel_mode_driver_framework_with_non_pnp_drivers">do not support Plug and Play</a> cannot use interrupt objects.)</p>

<p>The system might not assign all of the interrupt resources that a device can support. For example, a driver would create eight interrupt objects for a device that is capable of supporting eight MSI messages. However, the system might assign only one message to the device. In that case, seven of the interrupt objects will be unused.</p>

<p>Typically, your driver should store interrupt-specific information, such as the copied contents of device interrupt registers, in the interrupt object's <a href="wdf.framework_object_context_space">context space</a>. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that the driver passes to <b>WdfInterruptCreate</b> should describe the context space.</p>

<p>For drivers using framework version 1.9 and earlier, the parent of each interrupt object is the device object that the interrupt belongs to. The driver cannot change this parent, and the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>. Beginning in version 1.11, <b>ParentObject</b> can be a framework device object or queue object. If the driver specifies a parent, the driver must set the <b>AutomaticSerialization</b> member of the configuration structure to TRUE. The driver can specify a parent for both interrupts at DIRQL and <a href="wdf.supporting_passive_level_interrupts">passive-level interrupts</a>.</p>

<p>If your driver provides <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> or <a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a> callback functions for the framework interrupt object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.</p>

<p>For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.</p>

<p>The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure and a WDF_OBJECT_ATTRIBUTES structure and then calls <b>WdfInterruptCreate</b>.</p>

<p>Drivers typically call the  <b>WdfInterruptCreate</b> method from an <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. Starting in KMDF version 1.11 and UMDF version 2.0, drivers can call <b>WdfInterruptCreate</b> from <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDriverDeviceAdd</i>, the <b>InterruptRaw</b>  and <b>InterruptTranslated</b>  members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure
must be NULL. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDevicePrepareHardware</i>, these members must both be valid.</p>

<p>If you are creating a wake-capable interrupt object, as described in <a href="wdf.using_an_interrupt_to_wake_a_device">Using an Interrupt to Wake a Device</a>, you must call <b>WdfInterruptCreate</b> from <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>.</p>

<p> Your driver must call <b>WdfInterruptCreate</b> once for each interrupt vector that its device requires. If the device supports message-signaled interrupts (MSI), the driver must create an interrupt object for each message that the device can support.</p>

<p>After the PnP manager assigns system resources to the device, the framework stores information about the device's assigned interrupt resources in the interrupt objects that the driver has created. (Drivers that <a href="wdf.using_kernel_mode_driver_framework_with_non_pnp_drivers">do not support Plug and Play</a> cannot use interrupt objects.)</p>

<p>The system might not assign all of the interrupt resources that a device can support. For example, a driver would create eight interrupt objects for a device that is capable of supporting eight MSI messages. However, the system might assign only one message to the device. In that case, seven of the interrupt objects will be unused.</p>

<p>Typically, your driver should store interrupt-specific information, such as the copied contents of device interrupt registers, in the interrupt object's <a href="wdf.framework_object_context_space">context space</a>. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that the driver passes to <b>WdfInterruptCreate</b> should describe the context space.</p>

<p>For drivers using framework version 1.9 and earlier, the parent of each interrupt object is the device object that the interrupt belongs to. The driver cannot change this parent, and the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>. Beginning in version 1.11, <b>ParentObject</b> can be a framework device object or queue object. If the driver specifies a parent, the driver must set the <b>AutomaticSerialization</b> member of the configuration structure to TRUE. The driver can specify a parent for both interrupts at DIRQL and <a href="wdf.supporting_passive_level_interrupts">passive-level interrupts</a>.</p>

<p>If your driver provides <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> or <a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a> callback functions for the framework interrupt object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.</p>

<p>For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.</p>

<p>The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure and a WDF_OBJECT_ATTRIBUTES structure and then calls <b>WdfInterruptCreate</b>.</p>

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
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552348">WDF_INTERRUPT_CONFIG_INIT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptCreate method%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>