---
UID: NS.ntddk._IMAGE_INFO
title: IMAGE_INFO
author: windows-driver-content
description: Used by driver's load-image routine (PLOAD_IMAGE_NOTIFY_ROUTINE) to specify image information.
old-location: kernel\image_info.htm
ms.assetid: D2CD2457-8DDF-4449-9DC1-F1E7472C87CA
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMAGE_INFO
req.alt-loc: Ntddk.h
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
ms.keywords: IMAGE_INFO, IMAGE_INFO, *PIMAGE_INFO
req.iface: 
---

# IMAGE_INFO structure



## -description
<p>Used by driver's load-image routine (<a href="https://msdn.microsoft.com/library/windows/hardware/mt764088">PLOAD_IMAGE_NOTIFY_ROUTINE</a>) to specify image information.</p>


## -syntax

````
typedef struct _IMAGE_INFO {
  union {
    ULONG Properties;
    struct {
    };
    ULONG ImageAddressingMode  :8;
    ULONG SystemModeImage  :1;
    ULONG ImageMappedToAllPids  :1;
    ULONG ExtendedInfoPresent  :1;
    ULONG MachineTypeMismatch  :1;
    ULONG ImageSignatureLevel  :4;
    ULONG ImageSignatureType  :3;
    ULONG ImagePartialMap  :1;
    ULONG Reserved  :12;
  };
  ULONG  ImageBase;
  ULONG  ImageSelector;
  SIZE_T ImageSize;
  ULONG  ImageSectionNumber;
} IMAGE_INFO, *PIMAGE_INFO;
````


## -struct-fields
<dl>

### -field <b><b>Properties</b></b>

<dd></dd>

### -field <b><b>ImageAddressingMode</b></b>

<dd>
<p>Always set to IMAGE_ADDRESSING_MODE_32BIT.</p>
</dd>

### -field <b><b>SystemModeImage</b></b>

<dd>
<p>Set either to one for newly loaded kernel-mode components, such as drivers, or to zero for images that are mapped into user space.</p>
</dd>

### -field <b><b>ImageMappedToAllPids</b></b>

<dd>
<p>Always set to zero.</p>
</dd>

### -field <b><b>ExtendedInfoPresent</b></b>

<dd>
<p>If the <b>ExtendedInfoPresent</b> flag is set, the <b>IMAGE_INFO</b> structure is part of a larger, extended version of the image information structure (see <a href="https://msdn.microsoft.com/library/windows/hardware/mt764084">IMAGE_INFO_EX</a>). Added in Windows Vista. For more information, see "Extended version of the image information structure" later in this Remarks section.</p>
</dd>

### -field <b><b>MachineTypeMismatch</b></b>

<dd>
<p>Always set to zero. Added in Windows 8/Windows Server 2012.</p>
</dd>

### -field <b><b>ImageSignatureLevel</b></b>

<dd>
<p>The level of signature with which code integrity has labeled the image. This value is one of the <code>#define SE_SIGNING_LEVEL_*</code> constants in ntddk.h. Added in Windows 8.1/Windows Server 2012 R2.</p>
</dd>

### -field <b><b>ImageSignatureType</b></b>

<dd>
<p>The type of signature with which code integrity has labeled the image. This value is a <b>SE_IMAGE_SIGNATURE_TYPE</b> enumeration value,  defined in ntddk.h. Added in Windows 8.1/Windows Server 2012 R2.</p>
</dd>

### -field <b><b>ImagePartialMap</b></b>

<dd>
<p>This value is non-zero if the image mapping view called out for is a partial view that does not map the entire image; 0 if the view maps the entire image. Added in Windows 10/Windows Server 2016.</p>
</dd>

### -field <b><b>Reserved</b></b>

<dd>
<p>Always set to zero.</p>
</dd>

### -field <b><b>ImageBase</b></b>

<dd>
<p>Set to the virtual base address of the image.</p>
</dd>

### -field <b><b>ImageSelector</b></b>

<dd>
<p>Always set to zero.</p>
</dd>

### -field <b><b>ImageSize</b></b>

<dd>
<p>Set to the virtual size, in bytes, of the image.</p>
</dd>

### -field <b><b>ImageSectionNumber</b></b>

<dd>
<p>Always set to zero.</p>
</dd>
</dl>

## -remarks
<p>If the <b>ExtendedInfoPresent</b> flag is set, the <b>IMAGE_INFO</b> structure is part of a larger, extended version of the image information structure, <a href="https://msdn.microsoft.com/library/windows/hardware/mt764084">IMAGE_INFO_EX</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt764088">PLOAD_IMAGE_NOTIFY_ROUTINE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559957">PsSetLoadImageNotifyRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt764084">IMAGE_INFO_EX</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IMAGE_INFO structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>