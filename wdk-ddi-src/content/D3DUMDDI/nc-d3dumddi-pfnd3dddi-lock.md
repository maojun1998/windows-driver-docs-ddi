---
UID: NC.d3dumddi.PFND3DDDI_LOCK
title: PFND3DDDI_LOCK
author: windows-driver-content
description: The Lock function locks the given resource or a surface within the resource.
old-location: display\lock.htm
ms.assetid: e2289073-d46a-4a12-8de7-30400e04cc22
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Lock
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

# PFND3DDDI_LOCK callback



## -description
<p>The <i>Lock</i> function locks the given resource or a surface within the resource. </p>


## -prototype

````
PFND3DDDI_LOCK Lock;

__checkReturn HRESULT APIENTRY Lock(
  _In_    HANDLE         hDevice,
  _Inout_ D3DDDIARG_LOCK *pData
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
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structure that describes the resource or surface within the resource to lock.</p>
</dd>
</dl>

## -returns
<p><i>Lock</i> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The resource is successfully locked.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p><i>Lock</i> could not allocate the required memory for it to complete.</p><dl>
<dt><b>D3DDDIERR_WASSTILLDRAWING</b></dt>
</dl><p>The resource was not idle when the Microsoft Direct3D runtime called the <i>Lock</i> function with the <b>DoNotWait</b> bit-field flag set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a>.</p>

<p> </p>

## -remarks
<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>Lock</i> function to lock a resource or a surface within the resource. This locked resource or surface can be read from or written to by using read and write operations from the CPU. When the runtime calls <i>Lock</i>, the user-mode display driver must call the runtime's <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> callback function to lock an allocation corresponding to the resource or surface. Note that because the user-mode display driver can allocate multiple allocations for each resource or surface, the user-mode display driver might be required to appropriately convert or process the allocation pointer that is returned from <b>pfnLockCb</b> before returning the <i>Lock</i> call to the runtime. </p>

<p>Typically, calls to <i>Lock</i> are followed by matching calls to the driver's <a href="https://msdn.microsoft.com/23cc9c64-99d4-4602-a1b0-234fe7fcc3da">Unlock</a> function before the driver receives any calls to its draw-primitive functions (that is, calls to <a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a>, <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a>, <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a>, and <a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a>). This order guarantees that a driver is never requested to draw from a locked resource. However, on occasion, when performing software transform and lighting, the runtime must call one of the driver's draw-primitive functions before unlocking a resource (currently, only vertex buffers exhibit this behavior). The runtime marks vertex buffers on which this uncommon behavior might occur with the <b>MightDrawFromLocked</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structures (that is, both at creation and at lock time). When the hardware actively renders from a locked vertex buffer, the driver is not required to take any special action because the runtime will not overwrite any data in the locked vertex buffer . </p>

<p>The runtime calls the user-mode display driver's <i>Lock</i> function to lock preallocated system memory surfaces as well. This operation allows the user-mode display driver to properly synchronize references to such surfaces that might be in the hardware command stream. The user-mode display driver can accomplish the synchronization by: </p>

<p>Flushing (that is, calling the runtime's <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> callback function) any outstanding commands as necessary.</p>

<p>Calling <b>pfnLockCb</b> with the appropriate allocation handle for commands that have already been submitted to hardware. </p>

<p>The user-mode display driver returns a pointer to the memory for the locked surface and the pitch of the surface in the <b>pSurfData</b> and <b>Pitch</b> members of the D3DDDIARG_LOCK structure. However, for preallocated system memory surfaces, the runtime ignores the driver-set memory and pitch, although the driver can still fail the <i>Lock</i> call (and thus fail back to the application). The runtime sets the <b>NotifyOnly</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structure to differentiate <i>Lock</i> calls that lock preallocated system memory surfaces from other <i>Lock</i> calls. </p>

<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>Lock</i> function to lock a resource or a surface within the resource. This locked resource or surface can be read from or written to by using read and write operations from the CPU. When the runtime calls <i>Lock</i>, the user-mode display driver must call the runtime's <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> callback function to lock an allocation corresponding to the resource or surface. Note that because the user-mode display driver can allocate multiple allocations for each resource or surface, the user-mode display driver might be required to appropriately convert or process the allocation pointer that is returned from <b>pfnLockCb</b> before returning the <i>Lock</i> call to the runtime. </p>

<p>Typically, calls to <i>Lock</i> are followed by matching calls to the driver's <a href="https://msdn.microsoft.com/23cc9c64-99d4-4602-a1b0-234fe7fcc3da">Unlock</a> function before the driver receives any calls to its draw-primitive functions (that is, calls to <a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a>, <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a>, <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a>, and <a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a>). This order guarantees that a driver is never requested to draw from a locked resource. However, on occasion, when performing software transform and lighting, the runtime must call one of the driver's draw-primitive functions before unlocking a resource (currently, only vertex buffers exhibit this behavior). The runtime marks vertex buffers on which this uncommon behavior might occur with the <b>MightDrawFromLocked</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structures (that is, both at creation and at lock time). When the hardware actively renders from a locked vertex buffer, the driver is not required to take any special action because the runtime will not overwrite any data in the locked vertex buffer . </p>

<p>The runtime calls the user-mode display driver's <i>Lock</i> function to lock preallocated system memory surfaces as well. This operation allows the user-mode display driver to properly synchronize references to such surfaces that might be in the hardware command stream. The user-mode display driver can accomplish the synchronization by: </p>

<p>Flushing (that is, calling the runtime's <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> callback function) any outstanding commands as necessary.</p>

<p>Calling <b>pfnLockCb</b> with the appropriate allocation handle for commands that have already been submitted to hardware. </p>

<p>The user-mode display driver returns a pointer to the memory for the locked surface and the pitch of the surface in the <b>pSurfData</b> and <b>Pitch</b> members of the D3DDDIARG_LOCK structure. However, for preallocated system memory surfaces, the runtime ignores the driver-set memory and pitch, although the driver can still fail the <i>Lock</i> call (and thus fail back to the application). The runtime sets the <b>NotifyOnly</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a> structure to differentiate <i>Lock</i> calls that lock preallocated system memory surfaces from other <i>Lock</i> calls. </p>

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
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_LOCK callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>