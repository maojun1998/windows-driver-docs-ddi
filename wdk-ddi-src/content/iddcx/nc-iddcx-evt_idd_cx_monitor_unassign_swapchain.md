---
UID: NC.iddcx.EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN
title: EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN is called by the OS to inform the driver that a swapchain associated with a monitor is not valid anymore.
old-location: display\evt_idd_cx_monitor_unassign_swapchain.htm
old-project: display
ms.assetid: 7e845805-0121-49b0-9c0c-0f63bed6a50c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: WcsTranslateColors
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
---

# EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN callback



## -description
<b>EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN</b> is called by the OS to inform the driver that a swapchain associated with a monitor is not valid anymore.


## -prototype

````
EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN EvtIddCxMonitorUnassignSwapchain;

NTSTATUS EvtIddCxMonitorUnassignSwapchain(
  _In_ IDDCX_MONITOR MonitorObject
)
{ ... }

typedef EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN;
````


## -parameters

### -param MonitorObject [in]


                    
                A handle by the OS to identify the monitor that has an invalid associated swapchain.

## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
_requires_same_
</td>
</tr>
</table>