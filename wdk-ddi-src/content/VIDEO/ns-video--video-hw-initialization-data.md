---
UID: NS.video._VIDEO_HW_INITIALIZATION_DATA
title: VIDEO_HW_INITIALIZATION_DATA
author: windows-driver-content
description: The VIDEO_HW_INITIALIZATION_DATA structure specifies the entry points and storage requirements for the miniport driver. This structure is created on the stack and initialized by the miniport driver's DriverEntry function.
old-location: display\video_hw_initialization_data.htm
ms.assetid: 1f6bc444-12d6-4406-891e-87dfca437284
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_HW_INITIALIZATION_DATA
req.alt-loc: video.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
ms.keywords: VIDEO_HW_INITIALIZATION_DATA, VIDEO_HW_INITIALIZATION_DATA, *PVIDEO_HW_INITIALIZATION_DATA
req.iface: 
req.product: Windows 10 or later.
---

# VIDEO_HW_INITIALIZATION_DATA structure



## -description
<p>The VIDEO_HW_INITIALIZATION_DATA structure specifies the entry points and storage requirements for the miniport driver. This structure is created on the stack and initialized by the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.</p>


## -syntax

````
typedef struct _VIDEO_HW_INITIALIZATION_DATA {
  ULONG                          HwInitDataSize;
  INTERFACE_TYPE                 AdapterInterfaceType;
  PVIDEO_HW_FIND_ADAPTER         HwFindAdapter;
  PVIDEO_HW_INITIALIZE           HwInitialize;
  PVIDEO_HW_INTERRUPT            HwInterrupt;
  PVIDEO_HW_START_IO             HwStartIO;
  ULONG                          HwDeviceExtensionSize;
  ULONG                          StartingDeviceNumber;
  PVIDEO_HW_RESET_HW             HwResetHw;
  PVIDEO_HW_TIMER                HwTimer;
  PVIDEO_HW_START_DMA            HwStartDma;
  PVIDEO_HW_POWER_SET            HwSetPowerState;
  PVIDEO_HW_POWER_GET            HwGetPowerState;
  PVIDEO_HW_GET_CHILD_DESCRIPTOR HwGetVideoChildDescriptor;
  PVIDEO_HW_QUERY_INTERFACE      HwQueryInterface;
  ULONG                          HwChildDeviceExtensionSize;
  PVIDEO_ACCESS_RANGE            HwLegacyResourceList;
  ULONG                          HwLegacyResourceCount;
  PVIDEO_HW_LEGACYRESOURCES      HwGetLegacyResources;
  BOOLEAN                        AllowEarlyEnumeration;
  ULONG                          Reserved;
} VIDEO_HW_INITIALIZATION_DATA, *PVIDEO_HW_INITIALIZATION_DATA;
````


## -struct-fields
<dl>

### -field <b>HwInitDataSize</b>

<dd>
<p>Is the size in bytes of this structure. In effect, this indicates the version of VIDEO_HW_INITIALIZATION_DATA being used.</p>
</dd>

### -field <b>AdapterInterfaceType</b>

<dd>
<p>Is currently ignored by the video port and should remain zero-initialized.</p>
</dd>

### -field <b>HwFindAdapter</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function, which is required for all miniport drivers.</p>
</dd>

### -field <b>HwInitialize</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/0e43de21-59e5-4368-8ea2-34fa52e99950">HwVidInitialize</a> function, which is required for all miniport drivers.</p>
</dd>

### -field <b>HwInterrupt</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function, which is required only if the miniport driver's adapter generates interrupts. Otherwise, this pointer must be <b>NULL</b>.</p>
</dd>

### -field <b>HwStartIO</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/82951291-cf3e-486b-ad0e-f347fefe0370">HwVidStartIO</a> function, which is required for all miniport drivers.</p>
</dd>

### -field <b>HwDeviceExtensionSize</b>

<dd>
<p>Specifies the size in bytes of the storage the miniport driver requires for its private, adapter-specific device extension. A miniport driver uses this storage to hold driver-determined per-adapter information, such as the mapped logical address ranges for the adapter registers and whatever context information the driver maintains about its I/O operations.</p>
<p>A pointer to the device extension is passed in every call made to the miniport driver's standard functions except <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>, <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>, and any <i>SvgaHwIoPortXxx</i> functions. The video port driver allocates the memory for the device extension and initializes it with zeros before it is passed to the miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function.</p>
</dd>

### -field <b>StartingDeviceNumber</b>

<dd>
<p>Must be set to zero.</p>
</dd>

### -field <b>HwResetHw</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/dae00663-17bd-461d-9b3f-febff2d9811b">HwVidResetHw</a> function, which is required for any miniport driver of an adapter that does not reset fully on a soft reboot of the machine. Drivers of SVGA adapters that are fully reset to a VGA standard character mode on receipt of an INT10, MODE3-type command usually set this to <b>NULL</b>.</p>
</dd>

### -field <b>HwTimer</b>

<dd>
<p>Pointer to a miniport driver's <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> function, which is optional. This pointer can be <b>NULL</b>.</p>
</dd>

### -field <b>HwStartDma</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>HwSetPowerState</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a> function, which is required for all miniport drivers.</p>
</dd>

### -field <b>HwGetPowerState</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a> function, which is required for all miniport drivers.</p>
</dd>

### -field <b>HwGetVideoChildDescriptor</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function, which is required for all miniport drivers.</p>
</dd>

### -field <b>HwQueryInterface</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a> function. This can be optionally implemented in a miniport driver that supports external programming interfaces for inter-device communication, such as <a href="wdkgloss.i#wdkgloss.inter_integrated_circuit__i2c_#wdkgloss.inter_integrated_circuit__i2c_"><i>I2C</i></a> (or I²C) support for MPEG decoders. Otherwise, this member should be set to <b>NULL</b>.</p>
</dd>

### -field <b>HwChildDeviceExtensionSize</b>

<dd>
<p>Is the size in bytes of the device extension associated with the display output device. The miniport driver should fill in this member only if the miniport driver needs to manage the monitor configuration data separately from the adapter board configuration.</p>
</dd>

### -field <b>HwLegacyResourceList</b>

<dd>
<p>Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a> structures. Each structure describes a device I/O port or memory range for the video adapter that is not listed in PCI configuration space.</p>
</dd>

### -field <b>HwLegacyResourceCount</b>

<dd>
<p>Is the number of elements in the array to which <b>HwLegacyResourceList</b> points.</p>
</dd>

### -field <b>HwGetLegacyResources</b>

<dd>
<p>Pointer to the miniport driver's <a href="https://msdn.microsoft.com/015086e9-70b4-4756-9945-c9da17829e90">HwVidLegacyResources</a> function, which enables the driver to specify its legacy resources based on its device and vendor IDs.</p>
</dd>

### -field <b>AllowEarlyEnumeration</b>

<dd>
<p>Allows the miniport driver to enumerate its child devices before the adapter is started; that is, the video port driver can call <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> before <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> when this member is set to <b>TRUE</b>.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for system use.</p>
</dd>
</dl>

## -remarks
<p>A miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function must initialize this structure with zeros before it sets relevant values in any member.</p>

<p>The video port driver will ignore the <b>HwLegacyResourceCount</b> and <b>HwLegacyResourceList</b> members when <b>HwGetLegacyResources</b> is initialized with a pointer to a <a href="https://msdn.microsoft.com/015086e9-70b4-4756-9945-c9da17829e90">HwVidLegacyResources</a> implementation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564131">EMULATOR_ACCESS_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570493">VideoPortZeroMemory</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/015086e9-70b4-4756-9945-c9da17829e90">HwVidLegacyResources</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_HW_INITIALIZATION_DATA structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>