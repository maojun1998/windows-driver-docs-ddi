---
UID: NS.d3dumddi._D3DDDI_LOCKFLAGS
title: D3DDDI_LOCKFLAGS
author: windows-driver-content
description: The D3DDDI_LOCKFLAGS structure identifies how to lock a resource.
old-location: display\d3dddi_lockflags.htm
ms.assetid: b9bc6607-3222-45d0-a0d8-18c815a41771
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_LOCKFLAGS
req.alt-loc: d3dumddi.h
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
ms.keywords: D3DDDI_LOCKFLAGS, D3DDDI_LOCKFLAGS
req.iface: 
---

# D3DDDI_LOCKFLAGS structure



## -description
<p>The D3DDDI_LOCKFLAGS structure identifies how to lock a resource.</p>


## -syntax

````
typedef struct _D3DDDI_LOCKFLAGS {
  union {
    struct {
      UINT ReadOnly  :1;
      UINT WriteOnly  :1;
      UINT NoOverwrite  :1;
      UINT Discard  :1;
      UINT RangeValid  :1;
      UINT AreaValid  :1;
      UINT BoxValid  :1;
      UINT NotifyOnly  :1;
      UINT MightDrawFromLocked  :1;
      UINT DoNotWait  :1;
      UINT Reserved  :22;
    };
    UINT   Value;
  };
} D3DDDI_LOCKFLAGS;
````


## -struct-fields
<dl>

### -field <b>ReadOnly</b>

<dd>
<p>A UINT value that specifies whether the locked resource can only be read from. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).</p>
</dd>

### -field <b>WriteOnly</b>

<dd>
<p>A UINT value that specifies whether the locked resource can only be written to. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).</p>
</dd>

### -field <b>NoOverwrite</b>

<dd>
<p>A UINT value that specifies whether the locked resource can have data appended to it but the existing data in the resource cannot be modified. This member is used only with Direct3D vertex buffer locks. </p>
<p>Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).</p>
</dd>

### -field <b>Discard</b>

<dd>
<p>A UINT value that specifies whether the entire locked resource is modified. Therefore, because the existing contents can be discarded, they require no preliminary processing.</p>
<p>Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).</p>
</dd>

### -field <b>RangeValid</b>

<dd>
<p>A UINT value that specifies whether the locked resource is linear.</p>
<p>Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).</p>
</dd>

### -field <b>AreaValid</b>

<dd>
<p>A UINT value that specifies whether the locked resource is a surface.</p>
<p>Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).</p>
</dd>

### -field <b>BoxValid</b>

<dd>
<p>A UINT value that specifies whether the locked resource is a volume.</p>
<p>Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).</p>
</dd>

### -field <b>NotifyOnly</b>

<dd>
<p>A UINT value that specifies whether the lock call is for notification only.</p>
<p>Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).</p>
</dd>

### -field <b>MightDrawFromLocked</b>

<dd>
<p>A UINT value that specifies whether the driver is possibly requested to draw from a vertex buffer even if the vertex buffer is locked by the Direct3D runtime. <b>MightDrawFromLocked</b> does not guarantee that the driver will receive calls to its <a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a>, <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a>, <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a>, and <a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a> functions following the call to <b>Lock</b>. <b>MightDrawFromLocked</b> is set only on vertex buffers that were created with the <b>MightDrawFromLocked</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure during create time.</p>
<p>Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).</p>
</dd>

### -field <b>DoNotWait</b>

<dd>
<p>A UINT value that specifies whether the user-mode display driver should wait for the resource to become idle. Setting <b>DoNotWait</b> indicates that the user-mode display driver should not wait for the resource to become idle.</p>
<p>Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 22 bits (0xFFFFFC00) of the 32-bit <b>Value</b> member to zeros.</p>
</dd>

### -field <b>Value</b>

<dd>
<p>A member in the union that is contained in D3DDDI_LOCKFLAGS that can hold one 32-bit value that identifies how to lock a resource.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_LOCKFLAGS structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>