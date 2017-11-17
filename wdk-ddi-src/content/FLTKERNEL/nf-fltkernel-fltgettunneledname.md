---
UID: NF.fltkernel.FltGetTunneledName
title: FltGetTunneledName
author: windows-driver-content
description: The FltGetTunneledName routine retrieves the tunneled name for a file, given the normalized name returned for the file by a previous call to FltGetFileNameInformation, FltGetFileNameInformationUnsafe, or FltGetDestinationFileNameInformation.
old-location: ifsk\fltgettunneledname.htm
ms.assetid: 760ee574-5ca5-4db1-8b47-009a12398076
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: ifsk
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetTunneledName
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
ms.keywords: FltGetTunneledName
req.iface: 
---

# FltGetTunneledName function



## -description
<p>The <b>FltGetTunneledName</b> routine retrieves the tunneled name for a file, given the normalized name returned for the file by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>. </p>


## -syntax

````
NTSTATUS FltGetTunneledName(
  _In_  PFLT_CALLBACK_DATA         CallbackData,
  _In_  PFLT_FILE_NAME_INFORMATION FileNameInformation,
  _Out_ PFLT_FILE_NAME_INFORMATION *RetTunneledFileNameInformation
);
````


## -parameters
<dl>

### -param <i>CallbackData</i> [in]

<dd>
<p>Pointer to the callback data structure for the I/O operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param <i>FileNameInformation</i> [in]

<dd>
<p>Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a> structure containing normalized name information returned by a previous call to  <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a> for the file. </p>
</dd>

### -param <i>RetTunneledFileNameInformation</i> [out]

<dd>
<p>Pointer to a caller-allocated variable that receives the address of a newly allocated structure containing the tunneled file name. If no tunneled name is found, this variable receives <b>NULL</b>. This parameter is required and cannot be <b>NULL</b> on input. </p>
</dd>
</dl>

## -returns
<p><b>FltGetTunneledName</b> returns STATUS_SUCCESS if the tunneled name is found or if there is no tunneled name for the file. Otherwise, it returns an NTSTATUS value, such as the following: </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p><b>FltGetTunneledName</b> encountered a pool allocation failure. This is an error code. </p>

<p> </p>

## -remarks
<p>File systems, such as NTFS and FAT, use a per-volume tunnel cache to briefly preserve file names and other metadata for files that are being renamed, linked to, or deleted. File name tunneling can cause the final component in normalized file name information returned by a preoperation call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a> to be invalidated. If a minifilter driver retrieves normalized file name information in the preoperation callback routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) for a create, hard-link, or rename operation, it must call <b>FltGetTunneledName</b> from its postoperation callback routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) to retrieve the correct file name information for the file. </p>

<p>Only normalized file name information is affected by tunneling. The Filter Manager cannot ensure that the final component is normalized until after the create, hard-link, or rename operation has actually occurred, because tunneling can cause a short name to be changed to a long name. Thus a minifilter driver must call <b>FltGetTunneledName</b> from its postoperation callback routine to determine whether the normalized file name information retrieved in the preoperation callback routine is valid. </p>

<p>For more information about normalized file name information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>. </p>

<p>Minifilter drivers that only retrieve short or opened file name information should not call <b>FltGetTunneledName</b>. </p>

<p>After calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a> in the preoperation callback routine, the minifilter driver must store the returned <i>FileNameInformation</i> pointer in the preoperation callback routine's <i>CompletionContext</i> structure so that the postoperation callback can pass this pointer in the <i>FileNameInformation</i> parameter to <b>FltGetTunneledName</b>. </p>

<p>The following paired operations can cause the file name <i>name</i> to be tunneled: </p>

<p>delete(<i>name</i>)/create(<i>name</i>)</p>

<p>delete(<i>name</i>)/rename(<i>source</i>, <i>name</i>)</p>

<p>rename(<i>name</i>, <i>newname</i>)/create(<i>name</i>)</p>

<p>rename(<i>name</i>, <i>newname</i>)/rename(<i>source</i>, <i>name</i>)</p>

<p>If no tunneled name is found for the file, the <i>RetTunneledFileNameInformation</i> parameter receives <b>NULL</b>. </p>

<p>After a successful call to <b>FltGetTunneledName</b>, the caller is responsible for releasing the <i>RetTunneledFileNameInformation</i> and <i>FileNameInformation</i> pointers when they are no longer needed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>. </p>

<p><b>FltGetTunneledName</b> should only be called from a minifilter driver's postoperation callback routine for IRP_MJ_CREATE or IRP_MJ_SET_INFORMATION. Calling <b>FltGetTunneledName</b> from a postoperation callback routine for any other type of I/O operation, or calling it from a preoperation callback routine, is a programming error. </p>

<p>The caller must not modify the contents of the structure returned in the <i>RetTunneledFileNameInformation</i> parameter, because this structure is cached by the Filter Manager so that all minifilter drivers can use it. </p>

<p>For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;amp;id=172190">Microsoft Knowledge Base Article 172190</a>. </p>

<p>File systems, such as NTFS and FAT, use a per-volume tunnel cache to briefly preserve file names and other metadata for files that are being renamed, linked to, or deleted. File name tunneling can cause the final component in normalized file name information returned by a preoperation call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a> to be invalidated. If a minifilter driver retrieves normalized file name information in the preoperation callback routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) for a create, hard-link, or rename operation, it must call <b>FltGetTunneledName</b> from its postoperation callback routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) to retrieve the correct file name information for the file. </p>

<p>Only normalized file name information is affected by tunneling. The Filter Manager cannot ensure that the final component is normalized until after the create, hard-link, or rename operation has actually occurred, because tunneling can cause a short name to be changed to a long name. Thus a minifilter driver must call <b>FltGetTunneledName</b> from its postoperation callback routine to determine whether the normalized file name information retrieved in the preoperation callback routine is valid. </p>

<p>For more information about normalized file name information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>. </p>

<p>Minifilter drivers that only retrieve short or opened file name information should not call <b>FltGetTunneledName</b>. </p>

<p>After calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a> in the preoperation callback routine, the minifilter driver must store the returned <i>FileNameInformation</i> pointer in the preoperation callback routine's <i>CompletionContext</i> structure so that the postoperation callback can pass this pointer in the <i>FileNameInformation</i> parameter to <b>FltGetTunneledName</b>. </p>

<p>The following paired operations can cause the file name <i>name</i> to be tunneled: </p>

<p>delete(<i>name</i>)/create(<i>name</i>)</p>

<p>delete(<i>name</i>)/rename(<i>source</i>, <i>name</i>)</p>

<p>rename(<i>name</i>, <i>newname</i>)/create(<i>name</i>)</p>

<p>rename(<i>name</i>, <i>newname</i>)/rename(<i>source</i>, <i>name</i>)</p>

<p>If no tunneled name is found for the file, the <i>RetTunneledFileNameInformation</i> parameter receives <b>NULL</b>. </p>

<p>After a successful call to <b>FltGetTunneledName</b>, the caller is responsible for releasing the <i>RetTunneledFileNameInformation</i> and <i>FileNameInformation</i> pointers when they are no longer needed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>. </p>

<p><b>FltGetTunneledName</b> should only be called from a minifilter driver's postoperation callback routine for IRP_MJ_CREATE or IRP_MJ_SET_INFORMATION. Calling <b>FltGetTunneledName</b> from a postoperation callback routine for any other type of I/O operation, or calling it from a preoperation callback routine, is a programming error. </p>

<p>The caller must not modify the contents of the structure returned in the <i>RetTunneledFileNameInformation</i> parameter, because this structure is cached by the Filter Manager so that all minifilter drivers can use it. </p>

<p>For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;amp;id=172190">Microsoft Knowledge Base Article 172190</a>. </p>

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
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543417">FltParseFileNameInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544301">FltReferenceFileNameInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetTunneledName routine%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>