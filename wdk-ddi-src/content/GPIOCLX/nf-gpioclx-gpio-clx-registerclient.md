---
UID: NF.gpioclx.GPIO_CLX_RegisterClient
title: GPIO_CLX_RegisterClient
author: windows-driver-content
description: The GPIO_CLX_RegisterClient method registers a general-purpose I/O (GPIO) controller driver as a client of the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_registerclient.htm
ms.assetid: C87385E0-7B3F-44DA-90D0-E644C58AB375
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: GPIO
req.header: gpioclx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GPIO_CLX_RegisterClient
req.alt-loc: Gpioclx.h
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
ms.keywords: GPIO_CLX_RegisterClient
req.iface: 
---

# GPIO_CLX_RegisterClient function



## -description
<p>The <b>GPIO_CLX_RegisterClient</b> method registers a general-purpose I/O (GPIO) controller driver as a client of the GPIO framework extension (GpioClx).</p>


## -syntax

````
NTSTATUS GPIO_CLX_RegisterClient(
  [in]      WDFDRIVER                        Driver,
  [in, out] PGPIO_CLIENT_REGISTRATION_PACKET RegistrationPacket,
  [in]      PUNICODE_STRING                  RegistryPath
);
````


## -parameters
<dl>

### -param <i>Driver</i> [in]

<dd>
<p>A WDFDRIVER handle to the framework driver object for the GPIO controller driver.</p>
</dd>

### -param <i>RegistrationPacket</i> [in, out]

<dd>
<p>A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains the caller's registration information. This structure contains pointers to the event callback functions that the GPIO controller driver implements. Additionally, this structure specifies the size of the device context that the GPIO controller driver requires for its internal configuration data and state information.</p>
</dd>

### -param <i>RegistryPath</i> [in]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the path name of the registry key for the  GPIO controller driver. This parameter should be the registry path name that was passed to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. For more information about driver registry keys, see <a href="NULL">Registry Trees for Devices and Drivers</a>.</p>
</dd>
</dl>

## -returns
<p><b>GPIO_CLX_RegisterClient</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The <i>Driver</i>, <i>RegistrationPacket</i>, or <i>RegistryPath</i> parameter is NULL.</p><dl>
<dt><b>STATUS_GPIO_INVALID_REGISTRATION_PACKET</b></dt>
</dl><p>The specified registration packet is not valid.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>Out of memory.</p>

<p> </p>

## -remarks
<p>The GPIO controller driver calls this method to register its event callback functions with GpioClx. Typically, the driver calls this method from its <b>DriverEntry</b> routine, which runs shortly after the driver is loaded into memory.</p>

<p>Later, just before the GPIO controller driver unloads, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439498">GPIO_CLX_UnregisterClient</a> method to cancel its registration with GpioClx.</p>

<p>The GPIO controller driver calls this method to register its event callback functions with GpioClx. Typically, the driver calls this method from its <b>DriverEntry</b> routine, which runs shortly after the driver is loaded into memory.</p>

<p>Later, just before the GPIO controller driver unloads, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439498">GPIO_CLX_UnregisterClient</a> method to cancel its registration with GpioClx.</p>

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
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439498">GPIO_CLX_UnregisterClient</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_RegisterClient method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>