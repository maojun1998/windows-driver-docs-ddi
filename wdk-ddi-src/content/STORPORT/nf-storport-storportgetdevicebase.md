---
UID: NF.storport.StorPortGetDeviceBase
title: StorPortGetDeviceBase
author: windows-driver-content
description: The StorPortGetDeviceBase routine maps an I/O address to system address space.
old-location: storage\storportgetdevicebase.htm
ms.assetid: 6d25f2fb-be77-480f-b07c-294ab8a4272e
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: Storage
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetDeviceBase
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
ms.keywords: StorPortGetDeviceBase
req.iface: 
req.product: Windows 10 or later.
---

# StorPortGetDeviceBase function



## -description
<p>The <b>StorPortGetDeviceBase</b> routine maps an I/O address to system address space. </p>


## -syntax

````
STORPORT_API PVOID StorPortGetDeviceBase(
  _In_ PVOID                 HwDeviceExtension,
  _In_ INTERFACE_TYPE        BusType,
  _In_ ULONG                 SystemIoBusNumber,
  _In_ STOR_PHYSICAL_ADDRESS IoAddress,
  _In_ ULONG                 NumberOfBytes,
  _In_ BOOLEAN               InIoSpace
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. </p>
</dd>

### -param <i>BusType</i> [in]

<dd>
<p>Specifies the interface type of the I/O bus on which the HBA is connected. The miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine obtains the value for this parameter from the <b>AdapterInterfaceType</b> member of the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a>.</p>
</dd>

### -param <i>SystemIoBusNumber</i> [in]

<dd>
<p>Specifies the system-assigned number of the I/O bus on which the HBA is connected. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine obtains the value for this parameter from the <b>SystemIoBusNumber</b> member of the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a>.</p>
</dd>

### -param <i>IoAddress</i> [in]

<dd>
<p>Specifies the bus-relative base address of a range used by the HBA. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine obtains the value for this parameter from one of the <b>AccessRanges</b> elements in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> if the port driver supplies range-configuration information. Otherwise, this address can be a value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567076">StorPortGetBusData</a> or a miniport driver-supplied default value. Avoid using a base address of zero because its successful return status can conflict with the error status (<b>NULL</b>).</p>
</dd>

### -param <i>NumberOfBytes</i> [in]

<dd>
<p>Specifies the size in bytes of the range that the mapping should cover. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine obtains the value of this parameter from the same <b>AccessRanges</b> element as <i>IoAddress</i> if the port driver supplies range configuration information. Otherwise, this value can be returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567076">StorPortGetBusData</a> or a miniport driver-supplied default. In any case, the driver must not access the hardware outside of the returned, mapped range.</p>
</dd>

### -param <i>InIoSpace</i> [in]

<dd>
<p>TRUE indicates the range to be mapped is in I/O space, and the miniport driver will pass mapped addresses in this range to the Storport <i>port</i> read/write routines to communicate with the HBA. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557390">HwStorFindAdapter</a> routine obtains the value of this parameter from the same <b>AccessRanges</b> element as <i>IoAddress</i>. Note that a miniport driver <i>must invert</i> the value of the <b>InMemorySpace</b> member in an ACCESS_RANGE-type element before it is passed to <b>StorPortGetDeviceBase</b> as the <i>InIoSpace</i> argument. <b>FALSE</b> indicates that the range to be mapped is in memory space. </p>
</dd>
</dl>

## -returns
<p>A mapped, logical base address corresponding to the bus-relative address supplied in the <i>IoAddress</i> parameter. </p>

## -remarks
<p>Every miniport driver must pass mapped, logical access range addresses to the Storport <i>port</i> read/write routines and the Storport <i>register</i> read/write routines when communicating with its HBA(s).</p>

<p>This routine supports only those addresses that were assigned to the driver by the system Plug and Play (PnP) manager.</p>

<p>Every miniport driver must pass mapped, logical access range addresses to the Storport <i>port</i> read/write routines and the Storport <i>register</i> read/write routines when communicating with its HBA(s).</p>

<p>This routine supports only those addresses that were assigned to the driver by the system Plug and Play (PnP) manager.</p>

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
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567061">StorPortFreeDeviceBase</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20StorPortGetDeviceBase routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>