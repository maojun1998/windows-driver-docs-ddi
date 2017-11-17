---
UID: NS.ntddk._PCI_EXPRESS_LINK_CONTROL_REGISTER
title: PCI_EXPRESS_LINK_CONTROL_REGISTER
author: windows-driver-content
description: The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure.
old-location: pci\pci_express_link_control_register.htm
ms.assetid: f4f8bd0d-fad7-4712-92ca-44d45969142d
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: PCI
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_EXPRESS_LINK_CONTROL_REGISTER
req.alt-loc: ntddk.h
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
ms.keywords: PCI_EXPRESS_LINK_CONTROL_REGISTER, PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER
req.iface: 
---

# PCI_EXPRESS_LINK_CONTROL_REGISTER structure



## -description
<p>The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure.</p>


## -syntax

````
typedef union _PCI_EXPRESS_LINK_CONTROL_REGISTER {
  struct {
    USHORT ActiveStatePMControl  :2;
    USHORT Rsvd1  :1;
    USHORT ReadCompletionBoundary  :1;
    USHORT LinkDisable  :1;
    USHORT RetrainLink  :1;
    USHORT CommonClockConfig  :1;
    USHORT ExtendedSynch  :1;
    USHORT EnableClockPowerManagement  :1;
    USHORT Rsvd2  :7;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_LINK_CONTROL_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_REGISTER;
````


## -struct-fields
<dl>

### -field <b>ActiveStatePMControl</b>

<dd>
<p>The level of active state power management that is enabled on the PCIe link. Possible values are:</p>
<p></p>
<dl>

### -field <a id="L0sAndL1EntryDisabled"></a><a id="l0sandl1entrydisabled"></a><a id="L0SANDL1ENTRYDISABLED"></a><b>L0sAndL1EntryDisabled</b>

<dd>
<p>L0s and L1 are both disabled.</p>
</dd>

### -field <a id="L0sEntryEnabled"></a><a id="l0sentryenabled"></a><a id="L0SENTRYENABLED"></a><b>L0sEntryEnabled</b>

<dd>
<p>L0s is enabled.</p>
</dd>

### -field <a id="L1EntryEnabled"></a><a id="l1entryenabled"></a><a id="L1ENTRYENABLED"></a><b>L1EntryEnabled</b>

<dd>
<p>L1 is enabled.</p>
</dd>

### -field <a id="L0sAndL1EntryEnabled"></a><a id="l0sandl1entryenabled"></a><a id="L0SANDL1ENTRYENABLED"></a><b>L0sAndL1EntryEnabled</b>

<dd>
<p>L0s and L1 are both enabled.</p>
</dd>
</dl>
</dd>

### -field <b>Rsvd1</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <b>ReadCompletionBoundary</b>

<dd>
<p>The read completion boundary (RCB) value for the root port or the root port upstream from the endpoint. If the bit is clear, the RCB is 64 byte. If the bit is set, the RCB is 128 byte. This member is not applicable for switch ports.</p>
</dd>

### -field <b>LinkDisable</b>

<dd>
<p>A single bit that indicates that the link is disabled. This member is not applicable for endpoint devices, PCIe-to-PCI or PCI-X bridges, and upstream ports of switches.</p>
</dd>

### -field <b>RetrainLink</b>

<dd>
<p>A single bit that is used to initiate retraining of the link. Reads of this bit always return zero. This member is not applicable for endpoint devices, PCIe-to-PCI or PCI-X bridges, and upstream ports of switches.</p>
</dd>

### -field <b>CommonClockConfig</b>

<dd>
<p>A single bit that indicates that this component and the component at the opposite end of the link are operating with a distributed common reference clock. If this bit is clear, this component and the component at the opposite end of the link are operating with an asynchronous reference clock.</p>
</dd>

### -field <b>ExtendedSynch</b>

<dd>
<p>A single bit that indicates that additional ordered sets are transmitted when exiting the L0s state and when in the recovery state.</p>
</dd>

### -field <b>EnableClockPowerManagement</b>

<dd>
<p>A single bit that indicates that clock power management is enabled.</p>
</dd>

### -field <b>Rsvd2</b>

<dd>
<p>Reserved.</p>
</dd>

### -field <b>AsUSHORT</b>

<dd>
<p>A USHORT representation of the contents of the PCI_EXPRESS_LINK_CONTROL_REGISTER structure.</p>
</dd>
</dl>

## -remarks
<p>The PCI_EXPRESS_LINK_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.</p>

<p>A PCI_EXPRESS_LINK_CONTROL_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_LINK_CONTROL_REGISTER union%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>