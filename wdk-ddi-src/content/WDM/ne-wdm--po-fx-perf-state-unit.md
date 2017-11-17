---
UID: NE.wdm._PO_FX_PERF_STATE_UNIT
title: PO_FX_PERF_STATE_UNIT
author: windows-driver-content
description: The PO_FX_PERF_STATE_UNIT enumeration contains values that describe the type of unit that is controlled by the performance states in a PO_FX_COMPONENT_PERF_SET.
old-location: kernel\po_fx_perf_state_unit.htm
ms.assetid: E16657AE-9EEF-4E36-AAC5-5BF822006F1C
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PO_FX_PERF_STATE_UNIT
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
req.irql: <= DISPATCH_LEVEL
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.iface: 
req.product: Windows 10 or later.
---

# PO_FX_PERF_STATE_UNIT enumeration



## -description
<p>The <b>PO_FX_PERF_STATE_UNIT</b> enumeration contains values that describe the type of unit that is controlled by the performance states in a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a>.</p>


## -syntax

````
typedef enum _PO_FX_PERF_STATE_UNIT { 
  PoFxPerfStateUnitOther,
  PoFxPerfStateUnitFrequency,
  PoFxPerfStateUnitBandwidth,
  PoFxPerfStateUnitMaximum
} PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT;
````


## -enum-fields
<dl>

### -field <a id="PoFxPerfStateUnitOther"></a><a id="pofxperfstateunitother"></a><a id="POFXPERFSTATEUNITOTHER"></a><b>PoFxPerfStateUnitOther</b>

<dd>
<p>Indicates that the performance states control a unit other than frequency or bandwidth.</p>
</dd>

### -field <a id="PoFxPerfStateUnitFrequency"></a><a id="pofxperfstateunitfrequency"></a><a id="POFXPERFSTATEUNITFREQUENCY"></a><b>PoFxPerfStateUnitFrequency</b>

<dd>
<p>Indicates that the performance states control frequency, measured in Hz.</p>
</dd>

### -field <a id="PoFxPerfStateUnitBandwidth"></a><a id="pofxperfstateunitbandwidth"></a><a id="POFXPERFSTATEUNITBANDWIDTH"></a><b>PoFxPerfStateUnitBandwidth</b>

<dd>
<p>Indicates that the performance states control bandwidth, measured in bits per second.</p>
</dd>

### -field <a id="PoFxPerfStateUnitMaximum"></a><a id="pofxperfstateunitmaximum"></a><a id="POFXPERFSTATEUNITMAXIMUM"></a><b>PoFxPerfStateUnitMaximum</b>

<dd>
<p>This value is reserved for system use.</p>
</dd>
</dl>

## -remarks
<p>The <b>Unit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> structure is a value from the <b>PO_FX_PERF_STATE_UNIT</b> enumeration.</p>

<p>The <b>Unit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> structure is a value from the <b>PO_FX_PERF_STATE_UNIT</b> enumeration.</p>

<p>The <b>Unit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> structure is a value from the <b>PO_FX_PERF_STATE_UNIT</b> enumeration.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939778">PoFxRegisterComponentPerfStates</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_PERF_STATE_UNIT enumeration%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>