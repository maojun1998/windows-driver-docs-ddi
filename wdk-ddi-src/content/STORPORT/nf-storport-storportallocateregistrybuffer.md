---
UID: NF.storport.StorPortAllocateRegistryBuffer
title: StorPortAllocateRegistryBuffer
author: windows-driver-content
description: The StorPortAllocateRegistryBuffer routine is called by the miniport driver to allocate a buffer that can be used to read and write registry data.
old-location: storage\storportallocateregistrybuffer.htm
ms.assetid: c8d03a63-4b6a-4e84-994b-0e205401e531
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
req.alt-api: StorPortAllocateRegistryBuffer
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
ms.keywords: StorPortAllocateRegistryBuffer
req.iface: 
req.product: Windows 10 or later.
---

# StorPortAllocateRegistryBuffer function



## -description
<p>The <b>StorPortAllocateRegistryBuffer</b> routine is called by the miniport driver to allocate a buffer that can be used to read and write registry data. </p>


## -syntax

````
STORPORT_API PUCHAR StorPortAllocateRegistryBuffer(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Length
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>Pointer to a long that indicates, on input, the length in bytes of the registry buffer that the caller requires. On output, <i>Length</i> is updated to reflect the actual size in bytes of the buffer that was allocated. </p>
</dd>
</dl>

## -returns
<p><b>StorPortAllocateRegistryBuffer</b> returns a pointer to the registry buffer that the caller requested, or <b>NULL</b> if some error prevents the memory from being allocated. </p>

## -remarks
<p>Each instantiation of a miniport driver can only have one registry buffer allocated at a time. If a miniport driver attempts to allocate more than one registry buffer, the allocation will fail and <b>StorPortAllocateRegistryBuffer</b> will return <b>NULL</b>.</p>

<p>Each instantiation of a miniport driver can only have one registry buffer allocated at a time. If a miniport driver attempts to allocate more than one registry buffer, the allocation will fail and <b>StorPortAllocateRegistryBuffer</b> will return <b>NULL</b>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567067">StorPortFreeRegistryBuffer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Storage\storage]:%20StorPortAllocateRegistryBuffer routine%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>