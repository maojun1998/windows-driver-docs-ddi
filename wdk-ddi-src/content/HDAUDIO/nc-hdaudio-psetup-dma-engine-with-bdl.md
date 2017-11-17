---
UID: NC.hdaudio.PSETUP_DMA_ENGINE_WITH_BDL
title: PSETUP_DMA_ENGINE_WITH_BDL
author: windows-driver-content
description: The SetupDmaEngineWithBdl routine sets up a DMA engine to use a caller-allocated DMA buffer.The function pointer type for a SetupDmaEngineWithBdl routine is defined as:
old-location: audio\setupdmaenginewithbdl.htm
ms.assetid: 2760579b-9922-4709-a049-a73f3abd5043
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: audio
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetupDmaEngineWithBdl
req.alt-loc: hdaudio.h
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
ms.keywords: SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
req.iface: 
---

# PSETUP_DMA_ENGINE_WITH_BDL callback



## -description
<p>The <i>SetupDmaEngineWithBdl</i> routine sets up a DMA engine to use a caller-allocated DMA buffer.</p>
<p>The function pointer type for a <i>SetupDmaEngineWithBdl</i> routine is defined as:</p>


## -prototype

````
PSETUP_DMA_ENGINE_WITH_BDL SetupDmaEngineWithBdl;

NTSTATUS SetupDmaEngineWithBdl(
  _In_  PVOID            context,
  _In_  HANDLE           handle,
  _In_  ULONG            bufferSize,
  _In_  ULONG            lvi,
  _In_  PHDAUDIO_BDL_ISR isr,
  _In_  PVOID            callbackContext,
  _Out_ PUCHAR           streamID,
  _Out_ PULONG           fifoSize
)
{ ... }
````


## -parameters
<dl>

### -param <i>context</i> [in]

<dd>
<p>Specifies the context value from the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a> structure.</p>
</dd>

### -param <i>handle</i> [in]

<dd>
<p>Handle that identifies the DMA engine. This handle value was obtained from a previous call to <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a> or <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>.</p>
</dd>

### -param <i>bufferSize</i> [in]

<dd>
<p>Specifies the size in bytes of the DMA buffer that the buffer descriptor list (BDL) array describes.</p>
</dd>

### -param <i>lvi</i> [in]

<dd>
<p>Specifies the last valid index (LVI). This parameter contains the index for the last valid buffer descriptor in the BDL. After the DMA engine processes this descriptor, it wraps back to the first descriptor in the list and continues processing. If the BDL contains <i>n</i> descriptors, they are numbered 0 to <i>n</i>-1. The <i>lvi</i> value must be at least 1; in other words, the BDL must contain at least two valid entries before the DMA engine can begin operation.</p>
</dd>

### -param <i>isr</i> [in]

<dd>
<p>Function pointer to the caller's ISR. If the caller sets the interrupt-on-completion (IOC) bit in one or more of the buffer descriptors in the BDL, the HD Audio bus driver calls the ISR each time an IOC interrupt occurs on the stream. This parameter is a function pointer of type HDAUDIO_BDL_ISR, which is defined in the following Remarks section.</p>
</dd>

### -param <i>callbackContext</i> [in]

<dd>
<p>Specifies a context value that the HD Audio bus driver passes to the ISR.</p>
</dd>

### -param <i>streamID</i> [out]

<dd>
<p>Retrieves the stream identifier. This parameter points to a caller-allocated UCHAR variable into which the routine writes the stream identifier that it assigns to the stream.</p>
</dd>

### -param <i>fifoSize</i> [out]

<dd>
<p>Retrieves the DMA engine's FIFO size in bytes. This parameter points to a caller-allocated UINT variable into which the routine writes the FIFO size.</p>
</dd>
</dl>

## -returns
<p><i>SetupDmaEngineWithBdl</i> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><p>Indicates that the caller is running at an IRQL that is too high.</p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p>Indicates that the <i>handle</i> parameter value is invalid.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>Indicates that one of the parameter values is incorrect (bad pointer or invalid stream format).</p><dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl><p>Indicates that the hardware programming timed out. If this occurs, the hardware might be in a compromised state.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl><p>Indicates that the DMA device or DMA buffer is not allocated or the stream is not in the Reset state.</p>

<p> </p>

## -remarks
<p>The <i>SetupDmaEngineWithBdl</i> routine is used in conjunction with the <a href="https://msdn.microsoft.com/4538ce8e-fccd-4862-b226-a99fe578a5fd">AllocateContiguousDmaBuffer</a> and <a href="https://msdn.microsoft.com/7aaf98cc-8a94-44e6-9fef-76e00db17405">FreeContiguousDmaBuffer</a> routines. These three routines are available only in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. This DDI does not include the <a href="https://msdn.microsoft.com/44fd988a-24b3-4587-88d9-30585800ffbf">AllocateDmaBuffer</a> and <a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateContiguousDmaBuffer</b>, <i>SetupDmaEngineWithBdl</i>, and <b>FreeContiguousDmaBuffer</b>. Unlike <i>SetupDmaEngineWithBdl</i>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer.</p>

<p>The caller must call <a href="https://msdn.microsoft.com/4538ce8e-fccd-4862-b226-a99fe578a5fd">AllocateContiguousDmaBuffer</a> to allocate storage in the system memory for both the DMA buffer and the BDL that describes the physical memory pages in the buffer. The BDL entries must reside in memory that is physically contiguous. The BDL and buffer memory must meet the alignment requirements that are described in the <i>Intel High Definition Audio Specification</i> (see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website).</p>

<p>Both the BDL and the buffer memory that it describes must remain valid during DMA operations. Following the call to <i>SetupDmaEngineWithBdl</i>, the BDL and buffer memory must remain valid as long as the DMA engine continues to use the buffer. The DMA engine uses the buffer until the function driver replaces the buffer by calling <i>SetupDmaEngineWithBdl</i> again or frees the DMA engine by calling <a href="https://msdn.microsoft.com/3f068ac0-2b18-4242-86de-7044ce558788">FreeDmaEngine</a>. The function driver is responsible for calling <a href="https://msdn.microsoft.com/7aaf98cc-8a94-44e6-9fef-76e00db17405">FreeContiguousDmaBuffer</a> to free the buffer and BDL when they are no longer required.</p>

<p>When allocating memory for the buffer, the caller must satisfy all hardware constraints for the address, length, and alignment of the physically contiguous blocks of memory that the BDL specifies. Thus, only clients with significant knowledge of the bus controller and system hardware should use the <i>SetupDmaEngineWithBdl</i> routine.</p>

<p>Before calling <i>SetupDmaEngineWithBdl</i> to configure a DMA engine, the client must call <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a> or <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a> to allocate the DMA engine. The handle parameter is the value obtained from the preceding call to Allocate <i>Xxx</i>DmaEngine.</p>

<p>The caller is responsible for programming the codec to manage the data transfers and to recognize the stream identifier.</p>

<p>A WDM audio driver calls this routine at pin-creation time during execution of its <b>NewStream</b> method (for example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>).</p>

<p>Following the call to <i>SetupDmaEngineWithBdl</i>, the DMA engine is in the Reset state. To start the DMA engine, call <a href="https://msdn.microsoft.com/05cfb827-e143-4d77-b378-e02dd381e429">SetDmaEngineState</a>.</p>

<p>Parameter <i>isr</i> specifies the ISR that the HD Audio bus driver is to call each time an IOC interrupt occurs on the stream. This parameter is a function pointer of type HDAUDIO_BDL_ISR, which is defined as:</p>

<p>The HD Audio bus driver calls the ISR with the same context value that the client specified in the context parameter of the preceding <i>SetupDmaEngineWithBdl</i> call. The <i>interruptBitMask</i> parameter contains the bits from the HD Audio controller device's stream status register that indicate the reason for the interrupt. The following table shows the meaning of the individual bits in <i>interruptBitMask</i>.</p>

<p>31:5</p>

<p>
        Unused.
       </p>

<p>4</p>

<p>
        Descriptor Error (DESE). If an error occurs during the fetch of a buffer descriptor, then the HD Audio controller sets the DESE bit to 1.</p>

<p>3</p>

<p>
        FIFO Error (FIFOE). If a FIFO error occurs (an overrun on an output stream or an underrun on an input stream), then the HD Audio controller sets the FIFOE bit to 1.</p>

<p>2</p>

<p>
        Buffer Completion Interrupt Status (BCIS). If the IOC bit is set to 1 in the command byte of the buffer descriptor, then the HD Audio controller sets the BCIS bit to 1 after the last sample of a buffer is processed.</p>

<p>1:0</p>

<p>
        Unused.
       </p>

<p> </p>

<p>The HD Audio bus driver sets the unused bits to zero. Instead of assuming that an IOC interrupt has occurred, the ISR must always check the <i>interruptBitMask</i> parameter to determine whether a stream error has occurred. For more information about the interrupt status bits shown in the preceding table, see the description of the stream status registers in the <i>Intel High Definition Audio Specification</i>.</p>

<p>The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer at any one time. Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the <i>Intel High Definition Audio Specification</i>.</p>

<p>The caller must allocate the buffer memory and BDL from the nonpaged pool.</p>

<p>The <i>SetupDmaEngineWithBdl</i> routine is used in conjunction with the <a href="https://msdn.microsoft.com/4538ce8e-fccd-4862-b226-a99fe578a5fd">AllocateContiguousDmaBuffer</a> and <a href="https://msdn.microsoft.com/7aaf98cc-8a94-44e6-9fef-76e00db17405">FreeContiguousDmaBuffer</a> routines. These three routines are available only in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. This DDI does not include the <a href="https://msdn.microsoft.com/44fd988a-24b3-4587-88d9-30585800ffbf">AllocateDmaBuffer</a> and <a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a> routines, which are never used in conjunction with <b>AllocateContiguousDmaBuffer</b>, <i>SetupDmaEngineWithBdl</i>, and <b>FreeContiguousDmaBuffer</b>. Unlike <i>SetupDmaEngineWithBdl</i>, which configures the DMA engine to use a previously allocated DMA buffer, <b>AllocateDmaBuffer</b> both allocates a DMA buffer and configures the DMA engine to use the buffer.</p>

<p>The caller must call <a href="https://msdn.microsoft.com/4538ce8e-fccd-4862-b226-a99fe578a5fd">AllocateContiguousDmaBuffer</a> to allocate storage in the system memory for both the DMA buffer and the BDL that describes the physical memory pages in the buffer. The BDL entries must reside in memory that is physically contiguous. The BDL and buffer memory must meet the alignment requirements that are described in the <i>Intel High Definition Audio Specification</i> (see the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website).</p>

<p>Both the BDL and the buffer memory that it describes must remain valid during DMA operations. Following the call to <i>SetupDmaEngineWithBdl</i>, the BDL and buffer memory must remain valid as long as the DMA engine continues to use the buffer. The DMA engine uses the buffer until the function driver replaces the buffer by calling <i>SetupDmaEngineWithBdl</i> again or frees the DMA engine by calling <a href="https://msdn.microsoft.com/3f068ac0-2b18-4242-86de-7044ce558788">FreeDmaEngine</a>. The function driver is responsible for calling <a href="https://msdn.microsoft.com/7aaf98cc-8a94-44e6-9fef-76e00db17405">FreeContiguousDmaBuffer</a> to free the buffer and BDL when they are no longer required.</p>

<p>When allocating memory for the buffer, the caller must satisfy all hardware constraints for the address, length, and alignment of the physically contiguous blocks of memory that the BDL specifies. Thus, only clients with significant knowledge of the bus controller and system hardware should use the <i>SetupDmaEngineWithBdl</i> routine.</p>

<p>Before calling <i>SetupDmaEngineWithBdl</i> to configure a DMA engine, the client must call <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a> or <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a> to allocate the DMA engine. The handle parameter is the value obtained from the preceding call to Allocate <i>Xxx</i>DmaEngine.</p>

<p>The caller is responsible for programming the codec to manage the data transfers and to recognize the stream identifier.</p>

<p>A WDM audio driver calls this routine at pin-creation time during execution of its <b>NewStream</b> method (for example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>).</p>

<p>Following the call to <i>SetupDmaEngineWithBdl</i>, the DMA engine is in the Reset state. To start the DMA engine, call <a href="https://msdn.microsoft.com/05cfb827-e143-4d77-b378-e02dd381e429">SetDmaEngineState</a>.</p>

<p>Parameter <i>isr</i> specifies the ISR that the HD Audio bus driver is to call each time an IOC interrupt occurs on the stream. This parameter is a function pointer of type HDAUDIO_BDL_ISR, which is defined as:</p>

<p>The HD Audio bus driver calls the ISR with the same context value that the client specified in the context parameter of the preceding <i>SetupDmaEngineWithBdl</i> call. The <i>interruptBitMask</i> parameter contains the bits from the HD Audio controller device's stream status register that indicate the reason for the interrupt. The following table shows the meaning of the individual bits in <i>interruptBitMask</i>.</p>

<p>31:5</p>

<p>
        Unused.
       </p>

<p>4</p>

<p>
        Descriptor Error (DESE). If an error occurs during the fetch of a buffer descriptor, then the HD Audio controller sets the DESE bit to 1.</p>

<p>3</p>

<p>
        FIFO Error (FIFOE). If a FIFO error occurs (an overrun on an output stream or an underrun on an input stream), then the HD Audio controller sets the FIFOE bit to 1.</p>

<p>2</p>

<p>
        Buffer Completion Interrupt Status (BCIS). If the IOC bit is set to 1 in the command byte of the buffer descriptor, then the HD Audio controller sets the BCIS bit to 1 after the last sample of a buffer is processed.</p>

<p>1:0</p>

<p>
        Unused.
       </p>

<p> </p>

<p>The HD Audio bus driver sets the unused bits to zero. Instead of assuming that an IOC interrupt has occurred, the ISR must always check the <i>interruptBitMask</i> parameter to determine whether a stream error has occurred. For more information about the interrupt status bits shown in the preceding table, see the description of the stream status registers in the <i>Intel High Definition Audio Specification</i>.</p>

<p>The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer at any one time. Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the <i>Intel High Definition Audio Specification</i>.</p>

<p>The caller must allocate the buffer memory and BDL from the nonpaged pool.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536411">HDAUDIO_BUFFER_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/44fd988a-24b3-4587-88d9-30585800ffbf">AllocateDmaBuffer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/05cfb827-e143-4d77-b378-e02dd381e429">SetDmaEngineState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PSETUP_DMA_ENGINE_WITH_BDL callback function%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>