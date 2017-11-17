---
UID: NS.wdm._PO_FX_PERF_STATE_CHANGE
title: PO_FX_PERF_STATE_CHANGE
author: windows-driver-content
description: The PO_FX_PERF_STATE_CHANGE structure contains information about a change to a performance state that is being requested by calling the PoFxIssueComponentPerfStateChange or PoFxIssueComponentPerfStateChangeMultiple routine.
old-location: kernel\po_fx_perf_state_change.htm
ms.assetid: AE7A79DE-0202-4816-A36C-5A15C4539392
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PO_FX_PERF_STATE_CHANGE
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
ms.keywords: PO_FX_PERF_STATE_CHANGE, PO_FX_PERF_STATE_CHANGE, *PPO_FX_PERF_STATE_CHANGE
req.iface: 
req.product: Windows 10 or later.
---

# PO_FX_PERF_STATE_CHANGE structure



## -description
<p>The <b>PO_FX_PERF_STATE_CHANGE</b> structure contains information about a change to a performance state that is being requested by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a> routine.</p>


## -syntax

````
typedef struct _PO_FX_PERF_STATE_CHANGE {
  ULONG Set;
  union {
    ULONG     StateIndex;
    ULONGLONG StateValue;
  };
} PO_FX_PERF_STATE_CHANGE, *PPO_FX_PERF_STATE_CHANGE;
````


## -struct-fields
<dl>

### -field <b>Set</b>

<dd>
<p>The index of the performance state set that is being changed within the collection of performance state sets for the component.</p>
</dd>

### -field <b>StateIndex</b>

<dd>
<p>For sets that represent a discrete number of performance states (that is, where the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> is <b>PoFxPerfStateTypeDiscrete</b>), this member is the index of the performance state to use for the new performance level.</p>
</dd>

### -field <b>StateValue</b>

<dd>
<p>For sets that represent a continuous distribution of performance states (that is, where the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> is <b>PoFxPerfStateTypeRange</b>), this member is the value of the performance state to use for the new performance level.</p>
</dd>
</dl>

## -remarks
<p>The <b>PO_FX_PERF_STATE_CHANGE</b> structure is used for the <i>PerfChange</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a> routine and the  <i>PerfChanges</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a> routine. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939769">PoFxIssueComponentPerfStateChange</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939772">PoFxIssueComponentPerfStateChangeMultiple</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_PERF_STATE_CHANGE structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>