---
UID: NC.netdispumdddi.PFN_REGISTER_DATARATE_NOTIFICATIONS
title: PFN_REGISTER_DATARATE_NOTIFICATIONS
author: windows-driver-content
description: Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current network bandwidth of the Miracast connection.The data type of this function is PFN_REGISTER_DATARATE_NOTIFICATIONS.
old-location: display\registerfordataratenotifications.htm
ms.assetid: 81500bb9-27f1-4688-b244-37dfd766f3c8
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RegisterForDataRateNotifications
req.alt-loc: Netdispumdddi.h
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
ms.keywords: NDK_SRQ, NDK_SRQ
req.iface: 
---

# PFN_REGISTER_DATARATE_NOTIFICATIONS callback



## -description
<p>Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current  network bandwidth of the Miracast connection.<p>The data type of this function is <b>PFN_REGISTER_DATARATE_NOTIFICATIONS</b>.</p>
</p>
<p>The data type of this function is <b>PFN_REGISTER_DATARATE_NOTIFICATIONS</b>.</p>


## -prototype

````
PFN_REGISTER_DATARATE_NOTIFICATIONS RegisterForDataRateNotifications;

NTSTATUS RegisterForDataRateNotifications(
  _In_     HANDLE                    hMiracastDeviceHandle,
  _In_opt_ PVOID                     pNotificationContext,
  _In_opt_ PFN_DATARATE_NOTIFICATION pfnDataRateNotify
)
{ ... }
````


## -parameters
<dl>

### -param <i>hMiracastDeviceHandle</i> [in]

<dd>
<p>A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.</p>
</dd>

### -param <i>pNotificationContext</i> [in, optional]

<dd>
<p>The context that will be passed to the <a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a> function when the Miracast data rate changes.</p>
</dd>

### -param <i>pfnDataRateNotify</i> [in, optional]

<dd>
<p>A pointer to the driver routine that will be called when the bit rate of the Miracast network link has changed. See Remarks for more info.</p>
<p>  The driver can supply a <b>NULL</b> value to unregister for notifications.</p>
</dd>
</dl>

## -returns
<p>If the operating system successfully registers or unregisters the driver for notifications, it returns <b>STATUS_SUCCESS</b>.</p>

<p>Otherwise, these error codes can be returned:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>One or more parameters are invalid.</p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The operating system cannot support quality of service (QoS) notifications, or the call to the function is made outside of the calling thread in which the operating system called <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> or <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions.</p>

<p> </p>

## -remarks
<p>The user-mode driver can optionally call this function to register for automatic calls to data rate notification callback functions once a second.</p>

<p>To unregister from notifications, the driver should supply a value of <b>NULL</b> for the <i>pfnDataRateNotify</i> parameter and for the <b>CurrentBitRate</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a> structure
pointed to by the <i>pWfdConnectionStats</i> parameter when it calls the <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> function. When the operating system receives <b>NULL</b> for both <i>pfnDataRateNotify</i> and <b>CurrentBitRate</b>, it will no longer provide notifications.</p>

<p>Also, if the operating system can no longer provide QoS data, it sets the <i>pDataRateStats</i> parameter to <b>NULL</b> when the <a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a>  function is called.</p>

<p>The function fails if the driver attempts to register while it is already registered, or if it attempts to unregister if it has already unregistered. The function fails if the call is made outside of the calling thread in which the operating system called <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> or <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions.</p>

<p>The user-mode driver can optionally call this function to register for automatic calls to data rate notification callback functions once a second.</p>

<p>To unregister from notifications, the driver should supply a value of <b>NULL</b> for the <i>pfnDataRateNotify</i> parameter and for the <b>CurrentBitRate</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a> structure
pointed to by the <i>pWfdConnectionStats</i> parameter when it calls the <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> function. When the operating system receives <b>NULL</b> for both <i>pfnDataRateNotify</i> and <b>CurrentBitRate</b>, it will no longer provide notifications.</p>

<p>Also, if the operating system can no longer provide QoS data, it sets the <i>pDataRateStats</i> parameter to <b>NULL</b> when the <a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a>  function is called.</p>

<p>The function fails if the driver attempts to register while it is already registered, or if it attempts to unregister if it has already unregistered. The function fails if the call is made outside of the calling thread in which the operating system called <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a> or <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
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
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_REGISTER_DATARATE_NOTIFICATIONS callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>