---
UID: NC.d3dumddi.PFND3DDDI_LOCKASYNC
title: PFND3DDDI_LOCKASYNC
author: windows-driver-content
description: The LockAsync function locks the specified resource or a surface within the resource.
old-location: display\lockasync.htm
ms.assetid: c8f76ebe-947a-45e4-abbc-f6020da929e8
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LockAsync
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
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
req.iface: 
---

# PFND3DDDI_LOCKASYNC callback



## -description
<p>The <i>LockAsync</i> function locks the specified resource or a surface within the resource. </p>


## -prototype

````
PFND3DDDI_LOCKASYNC LockAsync;

__checkReturn HRESULT APIENTRY LockAsync(
  _In_    HANDLE              hDevice,
  _Inout_ D3DDDIARG_LOCKASYNC *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pData</i> [in, out]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a> structure that describes the resource or surface within the resource to lock.</p>
</dd>
</dl>

## -returns
<p><i>LockAsync</i> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The resource is successfully locked.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p><i>LockAsync</i> could not allocate the required memory for it to complete.</p><dl>
<dt><b>D3DDDIERR_WASSTILLDRAWING</b></dt>
</dl><p>Renaming the allocation that corresponds to the resource that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a> structure specifies failed. </p>

<p>The driver returns this value only if the <b>Discard</b> bit-field flag was set in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC.</p><dl>
<dt><b>E_NOTIMPL</b></dt>
</dl><p>The user-mode display driver does not support <i>LockAsync</i> for the specified resource.</p>

<p> </p>

## -remarks
<p>On multiple-processor computers, the Microsoft Direct3D runtime might call most functions of the user-mode display driver from a worker thread instead of from the main application thread. This multiple-processor optimization is transparent to the user-mode display driver. When the runtime uses multiple-processor optimization, it might call <i>LockAsync</i> rather than the <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function to lock a resource. </p>

<p>A user-mode display driver optionally implements <i>LockAsync</i>; the Direct3D runtime calls <i>LockAsync</i> only if the driver implements the <i>LockAsync</i>, <a href="https://msdn.microsoft.com/6af04c22-e559-4328-a20a-034b443fddc6">UnlockAsync</a>, and <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> functions. However, a user-mode display driver should implement <i>LockAsync</i> and the <i>UnlockAsync</i> and <i>Rename</i> functions because applications that frequently lock dynamic resources can then achieve higher performance. </p>

<p>When the Direct3D runtime uses multiple-processor optimization, it calls most user-mode display driver functions from a worker thread that the runtime manages; however, the runtime calls <i>LockAsync</i> on the application's main thread. </p>

<p>If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the DriverVersion member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a> function), the Direct3D runtime will call LockAsync in a reentrant manner. When the runtime calls LockAsync in a reentrant manner, one thread can execute inside LockAsync while another thread that references the same display device executes inside of another user-mode display driver function. Additionally, on this type of driver, the runtime will call LockAsync for system memory surfaces. If the <b>Discard</b> bit-field flag is set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>, the driver should attempt to rename the allocation that corresponds to the resource. Typically, to rename an allocation, the driver calls the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function with the allocation handle that corresponds to the resource to be locked. </p>

<p>The driver should set the <b>Discard</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure when the driver calls <b>pfnLockCb</b>. The driver should set the <b>NoExistingReference</b> bit-field flag of D3DDDICB_LOCK when the driver calls <b>pfnLockCb</b> only if the <b>NoExistingReferences</b> bit-field flag is set to <b>TRUE</b> in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, and the driver has no internally queued references to the resource. </p>

<p>If the driver fails to rename the allocation, the driver's <i>LockAsync</i> function should return the failure back to the runtime, and the driver should not flush its command buffer. If the renaming succeeds, the driver should return pointers to resource memory, pitch, and slice pitch and a handle to the resource that represents the renamed allocation in the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>. The driver should not update its internal tracking structures with the new allocation handle that <b>pfnLockCb</b> returns. Instead, the driver should wait until its <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> function is called. </p>

<p>If the <b>NoOverwrite</b> bit-field flag is set in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, the driver should lock the corresponding allocation with no-overwrite semantics. The driver should call <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> with the <b>IgnoreSync</b> bit-field flag set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> and should then return pointers to resource memory, pitch, and slice pitch to the Direct3D runtime in the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>. If the driver returns success (S_OK) from a call to its <i>LockAsync</i> with the <b>NoOverwrite</b> bit-field flag set, it might be called to render with a locked surface. The driver should return success from a call to its <i>LockAsync</i> with <b>NoOverwrite</b> set only for surfaces that can be rendered while locked. The video memory manager requires that the allocations that correspond to the surfaces must be supported in AGP or aperture segments; otherwise, calls to the <b>pfnRenderCb</b> function fail when the command buffer references a locked allocation.</p>

<p>In summary, the driver should fail calls to its <i>LockAsync</i> function if renaming fails or if no-overwrite semantics are not supported for the resource. However, the Direct3D runtime will recover from these failures. For all other situations, drivers should return success from <i>LockAsync</i> to improve performance on multiple-processor computers.</p>

<p>On multiple-processor computers, the Microsoft Direct3D runtime might call most functions of the user-mode display driver from a worker thread instead of from the main application thread. This multiple-processor optimization is transparent to the user-mode display driver. When the runtime uses multiple-processor optimization, it might call <i>LockAsync</i> rather than the <a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a> function to lock a resource. </p>

<p>A user-mode display driver optionally implements <i>LockAsync</i>; the Direct3D runtime calls <i>LockAsync</i> only if the driver implements the <i>LockAsync</i>, <a href="https://msdn.microsoft.com/6af04c22-e559-4328-a20a-034b443fddc6">UnlockAsync</a>, and <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> functions. However, a user-mode display driver should implement <i>LockAsync</i> and the <i>UnlockAsync</i> and <i>Rename</i> functions because applications that frequently lock dynamic resources can then achieve higher performance. </p>

<p>When the Direct3D runtime uses multiple-processor optimization, it calls most user-mode display driver functions from a worker thread that the runtime manages; however, the runtime calls <i>LockAsync</i> on the application's main thread. </p>

<p>If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the DriverVersion member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541724">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a> function), the Direct3D runtime will call LockAsync in a reentrant manner. When the runtime calls LockAsync in a reentrant manner, one thread can execute inside LockAsync while another thread that references the same display device executes inside of another user-mode display driver function. Additionally, on this type of driver, the runtime will call LockAsync for system memory surfaces. If the <b>Discard</b> bit-field flag is set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>, the driver should attempt to rename the allocation that corresponds to the resource. Typically, to rename an allocation, the driver calls the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function with the allocation handle that corresponds to the resource to be locked. </p>

<p>The driver should set the <b>Discard</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> structure when the driver calls <b>pfnLockCb</b>. The driver should set the <b>NoExistingReference</b> bit-field flag of D3DDDICB_LOCK when the driver calls <b>pfnLockCb</b> only if the <b>NoExistingReferences</b> bit-field flag is set to <b>TRUE</b> in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, and the driver has no internally queued references to the resource. </p>

<p>If the driver fails to rename the allocation, the driver's <i>LockAsync</i> function should return the failure back to the runtime, and the driver should not flush its command buffer. If the renaming succeeds, the driver should return pointers to resource memory, pitch, and slice pitch and a handle to the resource that represents the renamed allocation in the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>. The driver should not update its internal tracking structures with the new allocation handle that <b>pfnLockCb</b> returns. Instead, the driver should wait until its <a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a> function is called. </p>

<p>If the <b>NoOverwrite</b> bit-field flag is set in the <b>Flags</b> member of D3DDDIARG_LOCKASYNC, the driver should lock the corresponding allocation with no-overwrite semantics. The driver should call <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> with the <b>IgnoreSync</b> bit-field flag set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a> and should then return pointers to resource memory, pitch, and slice pitch to the Direct3D runtime in the members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>. If the driver returns success (S_OK) from a call to its <i>LockAsync</i> with the <b>NoOverwrite</b> bit-field flag set, it might be called to render with a locked surface. The driver should return success from a call to its <i>LockAsync</i> with <b>NoOverwrite</b> set only for surfaces that can be rendered while locked. The video memory manager requires that the allocations that correspond to the surfaces must be supported in AGP or aperture segments; otherwise, calls to the <b>pfnRenderCb</b> function fail when the command buffer references a locked allocation.</p>

<p>In summary, the driver should fail calls to its <i>LockAsync</i> function if renaming fails or if no-overwrite semantics are not supported for the resource. However, the Direct3D runtime will recover from these failures. For all other situations, drivers should return success from <i>LockAsync</i> to improve performance on multiple-processor computers.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543213">D3DDDIARG_LOCKASYNC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544205">D3DDDICB_LOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e2289073-d46a-4a12-8de7-30400e04cc22">Lock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/60f733e1-d376-4372-b1cc-39508b3a98e5">Rename</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6af04c22-e559-4328-a20a-034b443fddc6">UnlockAsync</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_LOCKASYNC callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>