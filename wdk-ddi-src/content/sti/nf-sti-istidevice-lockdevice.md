---
UID: NF.sti.IStiDevice.LockDevice
title: IStiDevice::LockDevice
author: windows-driver-content
description: The IStiDevice::LockDevice method locks a device for exclusive use by the caller.
old-location: image\istidevice_lockdevice.htm
ms.assetid: 208d9dc3-736b-4684-b8d3-802f6df78142
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: image
req.header: sti.h
req.include-header: Sti.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IStiDevice.LockDevice
req.alt-loc: sti.h
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
ms.keywords: IStiDevice, LockDevice, IStiDevice::LockDevice
req.iface: IStiDevice
req.product: Windows 10 or later.
---

# IStiDevice::LockDevice method



## -description
<p>The <b>IStiDevice::LockDevice </b>method locks a device for exclusive use by the caller.</p>


## -syntax

````
HRESULT LockDevice(
  [in] DWORD dwTimeOut
);
````


## -parameters
<dl>

### -param <i>dwTimeOut</i> [in]

<dd>
<p>Caller-supplied time-out value, in milliseconds. If the lock is not obtained in this time period, an error is returned.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

## -remarks
<p>Clients of the <b>IStiDevice</b> COM interface must call <b>IStiDevice::LockDevice</b> before calling the following methods:</p><dl>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543740">IStiDevice::Escape</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543752">IStiDevice::GetStatus</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543760">IStiDevice::RawReadData</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>
</p>
</dd>
</dl><p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543740">IStiDevice::Escape</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543752">IStiDevice::GetStatus</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543760">IStiDevice::RawReadData</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>
</p>

<p>If the <b>IStiDevice::LockDevice</b> method is able to obtain an <b>IStiDevice</b>-level lock on the device within the specified time-out period, it then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543829">IStiUSD::LockDevice</a> in the appropriate vendor-supplied minidriver.</p>

<p>Each call to <b>IStiDevice::LockDevice</b> must be paired with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.</p>

<p>Before calling <b>IStiDevice::LockDevice</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.</p>

<p>Clients of the <b>IStiDevice</b> COM interface must call <b>IStiDevice::LockDevice</b> before calling the following methods:</p><dl>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543740">IStiDevice::Escape</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543752">IStiDevice::GetStatus</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543760">IStiDevice::RawReadData</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>
</p>
</dd>
<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>
</p>
</dd>
</dl><p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543740">IStiDevice::Escape</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543752">IStiDevice::GetStatus</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543760">IStiDevice::RawReadData</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>
</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>
</p>

<p>If the <b>IStiDevice::LockDevice</b> method is able to obtain an <b>IStiDevice</b>-level lock on the device within the specified time-out period, it then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543829">IStiUSD::LockDevice</a> in the appropriate vendor-supplied minidriver.</p>

<p>Each call to <b>IStiDevice::LockDevice</b> must be paired with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.</p>

<p>Before calling <b>IStiDevice::LockDevice</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Sti.h (include Sti.h)</dt>
</dl>
</td>
</tr>
</table>