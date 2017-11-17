---
UID: NS.drmk.PKSP_DRMAUDIOSTREAM_CONTENTID
title: PKSP_DRMAUDIOSTREAM_CONTENTID
author: windows-driver-content
description: The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions.
old-location: audio\ksp_drmaudiostream_contentid.htm
ms.assetid: 16a83c46-c183-4dc2-9d98-877976cf5750
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: audio
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSP_DRMAUDIOSTREAM_CONTENTID
req.alt-loc: drmk.h
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
ms.keywords: PKSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID
req.iface: IDrmAudioStream
---

# PKSP_DRMAUDIOSTREAM_CONTENTID structure



## -description
<p>The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request. It also specifies a list of function pointers to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM functions</a>.</p>


## -syntax

````
typedef struct {
  KSPROPERTY                         Property;
  PVOID                              Context;
  PFNDRMADDCONTENTHANDLERS           DrmAddContentHandlers;
  PFNDRMCREATECONTENTMIXED           DrmCreateContentMixed;
  PFNDRMDESTROYCONTENT               DrmDestroyContent;
  PFNDRMFORWARDCONTENTTODEVICEOBJECT DrmForwardContentToDeviceObject;
  PFNDRMFORWARDCONTENTTOFILEOBJECT   DrmForwardContentToFileObject;
  PFNDRMFORWARDCONTENTTOINTERFACE    DrmForwardContentToInterface;
  PFNDRMGETCONTENTRIGHTS             DrmGetContentRights;
} KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID;
````


## -struct-fields
<dl>

### -field <b>Property</b>

<dd>
<p>Specifies the property to get or set. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.</p>
</dd>

### -field <b>Context</b>

<dd>
<p>Pointer to context data. This is the context specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> function's <i>DrmForward</i> parameter.</p>
</dd>

### -field <b>DrmAddContentHandlers</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a> function.</p>
</dd>

### -field <b>DrmCreateContentMixed</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a> function.</p>
</dd>

### -field <b>DrmDestroyContent</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a> function.</p>
</dd>

### -field <b>DrmForwardContentToDeviceObject</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> function.</p>
</dd>

### -field <b>DrmForwardContentToFileObject</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536352">DrmForwardContentToFileObject</a> function.</p>
</dd>

### -field <b>DrmForwardContentToInterface</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a> function.</p>
</dd>

### -field <b>DrmGetContentRights</b>

<dd>
<p>Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a> function.</p>
</dd>
</dl>

## -remarks
<p>The structure contains function pointers to the DRM library functions in order to provide the driver with convenient access to these functions.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Drmk.h (include Drmk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536352">DrmForwardContentToFileObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSP_DRMAUDIOSTREAM_CONTENTID structure%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>