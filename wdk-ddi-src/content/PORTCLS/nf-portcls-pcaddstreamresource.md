---
UID: NF.portcls.PcAddStreamResource
title: PcAddStreamResource
author: windows-driver-content
description: PcAddStreamResource adds a stream resource.
old-location: audio\pcaddstreamresource.htm
ms.assetid: CADB17C6-07EA-4497-AA73-4AECCC1D0A45
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: audio
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcAddStreamResource
req.alt-loc: NA
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: NA
req.irql: PASSIVE_LEVEL
ms.keywords: PcAddStreamResource
req.iface: 
---

# PcAddStreamResource function



## -description
<p>PcAddStreamResource adds a stream resource. 
Two type of stream resources are supported: interrupts and driver-owned threads. PcAddStreamResource can be called by any non-audio WaveRT miniport driver that has interrupts/threads associated with an audio stream. It can also be called by audio WaveRT miniport drivers.</p>


## -syntax

````
NTSTATUS  PcAddStreamResource(
  _In_  PDEVICE_OBJECT               PhysicalDeviceObject,
  _In_  PVOID                        ResourceSet,
  _In_  PPCSTREAMRESOURCE_DESCRIPTOR     ResourceDescriptor,
  _Out_ PCSTREAMRESOURCE*            ResourceHandle
);
````


## -parameters
<dl>

### -param <i>PhysicalDeviceObject</i> [in]

<dd>
<p>PDEVICE_OBJECT - The PDO of the device stack using this resource. </p>
</dd>

### -param <i>ResourceSet</i> [in]

<dd>
<p>PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time. </p>
</dd>

### -param <i>    ResourceDescriptor</i> [in]

<dd>
<p>PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a>. </p>
</dd>

### -param <i>ResourceHandle</i> [out]

<dd>
<p>PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>.  </p>
</dd>
</dl>

## -returns
<p>STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 </p>

<p>STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 

</p>

<p>Additional standard status codes may be returned.</p>

## -remarks
<p>To help ensure glitch-free operation, audio drivers must register their streaming resources with portcls. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. </p>

<p>All audio drivers must register their stream resources with the audio class driver. Driver registers the following resource types: interrupts, driver-owned threads and dependencies on other audio stack’s resources (example: parallel audio driver stacks). See the definition of <a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a> for more information.  </p>

<p>Audio driver must make sure the resource is valid when making this call.</p>

<p>Audio drivers that only run in Windows 10 can use  <b>PcAddStreamResource</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>. For Audio waveRT miniport drivers that need to also run under previous versions of Windows, use <a href="https://msdn.microsoft.com/F9F7E13B-E8D1-4B02-9CC5-737145DEFEB9">AddStreamResource</a> and <a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>. </p>

<p>To help ensure glitch-free operation, audio drivers must register their streaming resources with portcls. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. </p>

<p>All audio drivers must register their stream resources with the audio class driver. Driver registers the following resource types: interrupts, driver-owned threads and dependencies on other audio stack’s resources (example: parallel audio driver stacks). See the definition of <a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a> for more information.  </p>

<p>Audio driver must make sure the resource is valid when making this call.</p>

<p>Audio drivers that only run in Windows 10 can use  <b>PcAddStreamResource</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>. For Audio waveRT miniport drivers that need to also run under previous versions of Windows, use <a href="https://msdn.microsoft.com/F9F7E13B-E8D1-4B02-9CC5-737145DEFEB9">AddStreamResource</a> and <a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NA</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcAddStreamResource function%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>