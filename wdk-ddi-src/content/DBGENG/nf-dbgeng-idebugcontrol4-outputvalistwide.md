---
UID: NF.dbgeng.IDebugControl4.OutputVaListWide
title: IDebugControl4::OutputVaListWide
author: windows-driver-content
description: The OutputVaListWide method formats a string and sends the result to the output callbacks that are registered with the engine's clients.
old-location: debugger\outputvalistwide.htm
ms.assetid: 34d25938-5640-4e32-949f-94605ac38fa0
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h, Stdarg.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl4.OutputVaListWide
req.alt-loc: dbgeng.h
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
ms.keywords: IDebugControl4, OutputVaListWide, IDebugControl4::OutputVaListWide
req.iface: IDebugControl4
---

# IDebugControl4::OutputVaListWide method



## -description
<p>The <b>OutputVaListWide</b>  method formats a string and sends the result to the <a href="debugger.using_input_and_output#output_callbacks#output_callbacks">output callbacks</a> that are registered with the engine's clients.</p>


## -syntax

````
HRESULT OutputVaListWide(
  [in] ULONG   Mask,
  [in] PCWSTR  Format,
  [in] va_list Args
);
````


## -parameters
<dl>

### -param <i>Mask</i> [in]

<dd>
<p>Specifies the output-type bit field.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for possible values.</p>
</dd>

### -param <i>Format</i> [in]

<dd>
<p>Specifies the format string, as in <b>printf</b>.  Typically, conversion characters work exactly as they do in C. For the floating-point conversion characters, the 64-bit argument is interpreted as a 32-bit floating-point number unless the <b>l</b>  modifier is used.</p>
<p>The <b>%p</b> conversion character is supported, but it represents a pointer in a target's address space.  It might not have any modifiers, and it uses the debugger's internal address formatting.  The following additional conversion characters are supported.</p>
<table>
<tr>
<th>Character</th>
<th>Argument type</th>
<th>Argument</th>
<th>Text printed</th>
</tr>
<tr>
<td>
<p><b>%p</b></p>
</td>
<td>
<p>ULONG64</p>
</td>
<td>
<p>Pointer in an address space.</p>
</td>
<td>
<p>The value of the pointer. </p>
</td>
</tr>
<tr>
<td>
<p><b>%N</b></p>
</td>
<td>
<p>DWORD_PTR (32 or 64 bits, depending on the host's architecture) </p>
</td>
<td>
<p>Pointer in the host's virtual address space.</p>
</td>
<td>
<p>The value of the pointer.  (This is equivalent to the standard C <b>%p</b> character.) </p>
</td>
</tr>
<tr>
<td>
<p><b>%I</b></p>
</td>
<td>
<p>ULONG64</p>
</td>
<td>
<p>Any 64-bit value.</p>
</td>
<td>
<p>The specified value.  If this is greater than 0xFFFFFFFF, it is printed as a 64-bit value; otherwise, it is printed as a 32-bit value.</p>
</td>
</tr>
<tr>
<td>
<p><b>%ma</b></p>
</td>
<td>
<p>ULONG64 </p>
</td>
<td>
<p>Address of a NULL-terminated ASCII string in the process's virtual address space.</p>
</td>
<td>
<p>The specified string.</p>
</td>
</tr>
<tr>
<td>
<p><b>%mu</b></p>
</td>
<td>
<p>ULONG64 </p>
</td>
<td>
<p>Address of a NULL-terminated Unicode string in the process's virtual address space.</p>
</td>
<td>
<p>The specified string.</p>
</td>
</tr>
<tr>
<td>
<p><b>%msa</b></p>
</td>
<td>
<p>ULONG64 </p>
</td>
<td>
<p>Address of an ANSI_STRING structure in the process's virtual address space.</p>
</td>
<td>
<p>The specified string.</p>
</td>
</tr>
<tr>
<td>
<p><b>%msu</b></p>
</td>
<td>
<p>ULONG64 </p>
</td>
<td>
<p>Address of a UNICODE_STRING structure in the process's virtual address space.</p>
</td>
<td>
<p>The specified string.</p>
</td>
</tr>
<tr>
<td>
<p><b>%y</b></p>
</td>
<td>
<p>ULONG64 </p>
</td>
<td>
<p>Address in the process's virtual address space of an item with symbol information.</p>
</td>
<td>
<p>String that contains the name of the specified symbol (and displacement, if any). </p>
</td>
</tr>
<tr>
<td>
<p><b>%ly</b></p>
</td>
<td>
<p>ULONG64 </p>
</td>
<td>
<p>Address in the process's virtual address space of an item with symbol information.</p>
</td>
<td>
<p>String that contains the name of the specified symbol (and displacement, if any), as well as any available source line information. </p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>Args</i> [in]

<dd>
<p>Specifies additional parameters that represent values to be inserted into the output during formatting.  <i>Args</i> must be initialized using <b>va_start</b>.  This method does not call <b>va_end</b>.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>When generating very large output strings, it is possible to reach the limits of the debugger engine or of the operating system.  For example, some versions of the debugger engine have a 16K character limit for a single output.  If you find that very large output is getting truncated, you might need to split your output into multiple requests.</p>

<p>When generating very large output strings, it is possible to reach the limits of the debugger engine or of the operating system.  For example, some versions of the debugger engine have a 16K character limit for a single output.  If you find that very large output is getting truncated, you might need to split your output into multiple requests.</p>

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
<dt>Dbgeng.h (include Dbgeng.h or Stdarg.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539252">ControlledOutputVaList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542750">dprintf</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::OutputVaListWide method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>