---
UID: NC.netdispumdddi.PFN_HANDLE_KMD_MESSAGE
title: PFN_HANDLE_KMD_MESSAGE
author: windows-driver-content
description: Called by the operating system to handle the asynchronous kernel-mode message that the Miracast user-mode driver receives when the display miniport driver calls the DxgkCbMiracastSendMessage function.
old-location: display\handlekernelmodemessage.htm
ms.assetid: 9DE4F3B0-915A-4C66-85F8-AE248B8471B5
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HandleKernelModeMessage
req.alt-loc: Netdispumdddi.h
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
ms.keywords: NDK_SRQ, NDK_SRQ
req.iface: 
---

# PFN_HANDLE_KMD_MESSAGE callback



## -description
<p>Called by the operating system to handle the asynchronous kernel-mode message that the Miracast user-mode driver receives when the display miniport driver calls the <a href="https://msdn.microsoft.com/E8C3B9E3-854C-488D-809B-0F0893591352">DxgkCbMiracastSendMessage</a> function.</p>


## -prototype

````
PFN_HANDLE_KMD_MESSAGE HandleKernelModeMessage;

NTSTATUS HandleKernelModeMessage(
  _In_  PVOID pMiracastContext,
  _In_  UINT  InputBufferSize,
  _In_  VOID  *pInputBuffer,
  _In_  UINT  OutputBufferSize,
  _Out_ VOID  *pOutputBuffer,
  _Out_ UINT  *pBytesReturned
)
{ ... }
````


## -parameters
<dl>

### -param <i>pMiracastContext</i> [in]

<dd>
<p>A pointer to a context associated with a display adapter.</p>
<p>The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.</p>
</dd>

### -param <i>InputBufferSize</i> [in]

<dd>
<p>The size of the input buffer <i>pInputBuffer</i>, supplied by the operating system.</p>
</dd>

### -param <i>pInputBuffer</i> [in]

<dd>
<p>A pointer to the input buffer, supplied by the operating system.</p>
</dd>

### -param <i>OutputBufferSize</i> [in]

<dd>
<p>The size of the output buffer <i>pOutputBuffer</i>, supplied by the operating system.</p>
</dd>

### -param <i>pOutputBuffer</i> [out]

<dd>
<p>A pointer to the output buffer, supplied by the operating system.</p>
</dd>

### -param <i>pBytesReturned</i> [out]

<dd>
<p>A pointer to a buffer, supplied by the operating system, that holds the number of returned bytes that the display miniport driver wrote in <i>pOutputBuffer</i>.</p>
</dd>
</dl>

## -returns
<p>On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.</p>

## -remarks
<p>When this function is called, it's possible that it has also been called in another thread. The driver is therefore responsible for synchronizing multiple calls to <i>HandleKernelModeMessage</i> if necessary.</p>

<p>The operating system guarantees that this function is not called when <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> are called. All the messages that the display miniport driver sends during the startup of a Miracast connected session (<i>StartMiracastSession</i>) are blocked until the session startup process has completed. The operating system also blocks all messages that the display miniport driver sends during or after a call to stop the Miracast session (<i>StopMiracastSession</i>).</p>

<p>When this function is called, it's possible that it has also been called in another thread. The driver is therefore responsible for synchronizing multiple calls to <i>HandleKernelModeMessage</i> if necessary.</p>

<p>The operating system guarantees that this function is not called when <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> are called. All the messages that the display miniport driver sends during the startup of a Miracast connected session (<i>StartMiracastSession</i>) are blocked until the session startup process has completed. The operating system also blocks all messages that the display miniport driver sends during or after a call to stop the Miracast session (<i>StopMiracastSession</i>).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/E8C3B9E3-854C-488D-809B-0F0893591352">DxgkCbMiracastSendMessage</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_HANDLE_KMD_MESSAGE callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>