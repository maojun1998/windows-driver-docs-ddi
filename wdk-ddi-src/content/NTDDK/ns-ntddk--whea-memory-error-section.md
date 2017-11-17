---
UID: NS.ntddk._WHEA_MEMORY_ERROR_SECTION
title: WHEA_MEMORY_ERROR_SECTION
author: windows-driver-content
description: The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.
old-location: whea\whea_memory_error_section.htm
ms.assetid: eede44f8-0e14-4256-9893-cbdb5ef4ef9b
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: whea
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_MEMORY_ERROR_SECTION
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
ms.keywords: WHEA_MEMORY_ERROR_SECTION, WHEA_MEMORY_ERROR_SECTION, *PWHEA_MEMORY_ERROR_SECTION
req.iface: 
---

# WHEA_MEMORY_ERROR_SECTION structure



## -description
<p>The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data.</p>


## -syntax

````
typedef struct _WHEA_MEMORY_ERROR_SECTION {
  WHEA_MEMORY_ERROR_SECTION_VALIDBITS ValidBits;
  WHEA_ERROR_STATUS                   ErrorStatus;
  ULONGLONG                           PhysicalAddress;
  ULONGLONG                           PhysicalAddressMask;
  USHORT                              Node;
  USHORT                              Card;
  USHORT                              Module;
  USHORT                              Bank;
  USHORT                              Device;
  USHORT                              Row;
  USHORT                              Column;
  USHORT                              BitPosition;
  ULONGLONG                           RequesterId;
  ULONGLONG                           ResponderId;
  ULONGLONG                           TargetId;
  UCHAR                               ErrorType;
} WHEA_MEMORY_ERROR_SECTION, *PWHEA_MEMORY_ERROR_SECTION;
````


## -struct-fields
<dl>

### -field <b>ValidBits</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560568">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.</p>
</dd>

### -field <b>ErrorStatus</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560514">WHEA_ERROR_STATUS</a> structure that contains memory error status data.</p>
<p>This member contains valid data only if the <b>Validbits.ErrorStatus</b> bit is set.</p>
</dd>

### -field <b>PhysicalAddress</b>

<dd>
<p>The physical address where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.PhysicalAddress</b> bit is set.</p>
</dd>

### -field <b>PhysicalAddressMask</b>

<dd>
<p>A bit mask that specifies which of the bits in the <b>PhysicalAddress</b> member contain valid address data.</p>
<p>This member contains valid data only if the <b>Validbits.PhysicalAddressMask</b> bit is set.</p>
</dd>

### -field <b>Node</b>

<dd>
<p>The identifier of the node that contains the memory where the memory error occurred in a system with multiple nodes.</p>
<p>This member contains valid data only if the <b>Validbits.Node</b> bit is set.</p>
</dd>

### -field <b>Card</b>

<dd>
<p>The card number of the card that contains the memory where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.Card</b> bit is set.</p>
</dd>

### -field <b>Module</b>

<dd>
<p>The module number of the module that contains the memory where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.Module</b> bit is set.</p>
</dd>

### -field <b>Bank</b>

<dd>
<p>The bank number of the memory bank that contains the memory where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.Bank</b> bit is set.</p>
</dd>

### -field <b>Device</b>

<dd>
<p>The device number of the memory device that contains the memory where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.Device</b> bit is set.</p>
</dd>

### -field <b>Row</b>

<dd>
<p>The row number of the location where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.Row</b> bit is set.</p>
</dd>

### -field <b>Column</b>

<dd>
<p>The column number of the location where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.Column</b> bit is set.</p>
</dd>

### -field <b>BitPosition</b>

<dd>
<p>The bit position where the memory error occurred.</p>
<p>This member contains valid data only if the <b>Validbits.BitPosition</b> bit is set.</p>
</dd>

### -field <b>RequesterId</b>

<dd>
<p>An identifier that uniquely identifies the requester associated with the error.</p>
<p>This member contains valid data only if the <b>Validbits.RequesterId</b> bit is set.</p>
</dd>

### -field <b>ResponderId</b>

<dd>
<p>An identifier that uniquely identifies the responder associated with the error.</p>
<p>This member contains valid data only if the <b>Validbits.ResponderId</b> bit is set.</p>
</dd>

### -field <b>TargetId</b>

<dd>
<p>The hardware address of the intended target of the transaction.</p>
<p>This member contains valid data only if the <b>Validbits.TargetId</b> bit is set.</p>
</dd>

### -field <b>ErrorType</b>

<dd>
<p>The type of memory error that occurred. Possible values are:</p>
<p></p>
<dl>

### -field <a id="WHEA_MEMERRTYPE_UNKNOWN"></a><a id="whea_memerrtype_unknown"></a>WHEA_MEMERRTYPE_UNKNOWN

<dd>
<p>An unknown error.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_NOERROR"></a><a id="whea_memerrtype_noerror"></a>WHEA_MEMERRTYPE_NOERROR

<dd>
<p>No error occurred.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_SINGLEBITECC"></a><a id="whea_memerrtype_singlebitecc"></a>WHEA_MEMERRTYPE_SINGLEBITECC

<dd>
<p>A single bit <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> error.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_MULTIBITECC"></a><a id="whea_memerrtype_multibitecc"></a>WHEA_MEMERRTYPE_MULTIBITECC

<dd>
<p>A multibit ECC error.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_SINGLESYMCHIPKILL"></a><a id="whea_memerrtype_singlesymchipkill"></a>WHEA_MEMERRTYPE_SINGLESYMCHIPKILL

<dd>
<p>A single symbol <a href="http://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> error.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_MULTISYMCHIPKILL"></a><a id="whea_memerrtype_multisymchipkill"></a>WHEA_MEMERRTYPE_MULTISYMCHIPKILL

<dd>
<p>A multiple symbol <a href="http://go.microsoft.com/fwlink/p/?linkid=81372">ChipKill</a> <a href="wdkgloss.e#wdkgloss.ecc#wdkgloss.ecc"><i>ECC</i></a> error.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_MASTERABORT"></a><a id="whea_memerrtype_masterabort"></a>WHEA_MEMERRTYPE_MASTERABORT

<dd>
<p>A master abort.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_TARGETABORT"></a><a id="whea_memerrtype_targetabort"></a>WHEA_MEMERRTYPE_TARGETABORT

<dd>
<p>A target abort.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_PARITYERROR"></a><a id="whea_memerrtype_parityerror"></a>WHEA_MEMERRTYPE_PARITYERROR

<dd>
<p>A parity error.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_WATCHDOGTIMEOUT"></a><a id="whea_memerrtype_watchdogtimeout"></a>WHEA_MEMERRTYPE_WATCHDOGTIMEOUT

<dd>
<p>A watchdog timeout.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_INVALIDADDRESS"></a><a id="whea_memerrtype_invalidaddress"></a>WHEA_MEMERRTYPE_INVALIDADDRESS

<dd>
<p>An invalid memory address.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_MIRRORBROKEN"></a><a id="whea_memerrtype_mirrorbroken"></a>WHEA_MEMERRTYPE_MIRRORBROKEN

<dd>
<p>A broken memory mirror.</p>
</dd>

### -field <a id="WHEA_MEMERRTYPE_MEMORYSPARING"></a><a id="whea_memerrtype_memorysparing"></a>WHEA_MEMERRTYPE_MEMORYSPARING

<dd>
<p>A memory sparing error.</p>
</dd>
</dl>
<p>This member contains valid data only if the <b>Validbits.ErrorType</b> bit is set.</p>
</dd>
</dl>

## -remarks
<p>The WHEA_MEMORY_ERROR_SECTION structure describes the error data that is contained in a platform memory error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a platform memory error section only if the <b>SectionType </b>member of one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains MEMORY_ERROR_SECTION_GUID.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560514">WHEA_ERROR_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560568">WHEA_MEMORY_ERROR_SECTION_VALIDBITS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_MEMORY_ERROR_SECTION structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>