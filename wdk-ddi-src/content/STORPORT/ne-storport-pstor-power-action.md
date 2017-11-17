---
UID: NE.storport.PSTOR_POWER_ACTION
title: PSTOR_POWER_ACTION
author: windows-driver-content
description: The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition.
old-location: storage\stor_power_action.htm
ms.assetid: ffc7c1ec-faec-4383-ab69-844cf68d054f
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: Storage
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_POWER_ACTION
req.alt-loc: storport.h
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
ms.keywords: STORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.iface: 
req.product: Windows 10 or later.
---

# PSTOR_POWER_ACTION enumeration



## -description
<p>The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition. </p>


## -syntax

````
typedef enum  { 
  StorPowerActionNone           = 0,
  StorPowerActionReserved       = 1,
  StorPowerActionSleep          = 2,
  StorPowerActionHibernate      = 3,
  StorPowerActionShutdown       = 4,
  StorPowerActionShutdownReset  = 5,
  StorPowerActionShutdownOff    = 6,
  StorPowerActionWarmEject      = 7
} STOR_POWER_ACTION, *PSTOR_POWER_ACTION;
````


## -enum-fields
<dl>

### -field <a id="StorPowerActionNone"></a><a id="storpoweractionnone"></a><a id="STORPOWERACTIONNONE"></a><b>StorPowerActionNone</b>

<dd>
<p>No system shutdown is about to occur.</p>
</dd>

### -field <a id="StorPowerActionReserved"></a><a id="storpoweractionreserved"></a><a id="STORPOWERACTIONRESERVED"></a><b>StorPowerActionReserved</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <a id="StorPowerActionSleep"></a><a id="storpoweractionsleep"></a><a id="STORPOWERACTIONSLEEP"></a><b>StorPowerActionSleep</b>

<dd>
<p>The system is entering standby.</p>
</dd>

### -field <a id="StorPowerActionHibernate"></a><a id="storpoweractionhibernate"></a><a id="STORPOWERACTIONHIBERNATE"></a><b>StorPowerActionHibernate</b>

<dd>
<p>The system is entering hibernation.</p>
</dd>

### -field <a id="StorPowerActionShutdown"></a><a id="storpoweractionshutdown"></a><a id="STORPOWERACTIONSHUTDOWN"></a><b>StorPowerActionShutdown</b>

<dd>
<p>The system is shutting down, but the type of shutdown is not known.</p>
</dd>

### -field <a id="StorPowerActionShutdownReset"></a><a id="storpoweractionshutdownreset"></a><a id="STORPOWERACTIONSHUTDOWNRESET"></a><b>StorPowerActionShutdownReset</b>

<dd>
<p>The system is shutting down and resetting.</p>
</dd>

### -field <a id="StorPowerActionShutdownOff"></a><a id="storpoweractionshutdownoff"></a><a id="STORPOWERACTIONSHUTDOWNOFF"></a><b>StorPowerActionShutdownOff</b>

<dd>
<p>The system is shutting down and powering off.</p>
</dd>

### -field <a id="StorPowerActionWarmEject"></a><a id="storpoweractionwarmeject"></a><a id="STORPOWERACTIONWARMEJECT"></a><b>StorPowerActionWarmEject</b>

<dd>
<p>The system is preparing for ejection.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565389">SCSI_POWER_REQUEST_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20STOR_POWER_ACTION enumeration%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>