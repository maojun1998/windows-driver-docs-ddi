---
UID: NE.extsfns._DEBUG_FLR_PARAM_TYPE
title: DEBUG_FLR_PARAM_TYPE
author: windows-driver-content
description: The values of DEBUG_FLR_PARAM_TYPE enumeration are tags that indicate the kind of information that is stored in failure analysis entry.
old-location: debugger\debug_flr_param_type.htm
ms.assetid: D57D356F-DC11-4C27-97D3-DF40BF2AB490
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: debugger
req.header: extsfns.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_FLR_PARAM_TYPE
req.alt-loc: extsfns.h
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
ms.keywords: EVENT_TRACE_HEADER, EVENT_TRACE_HEADER, *PEVENT_TRACE_HEADER
req.iface: ExtRemoteTypedList
---

# DEBUG_FLR_PARAM_TYPE enumeration



## -description
<p>The values of <b>DEBUG_FLR_PARAM_TYPE</b> enumeration are tags that indicate the kind of information that is stored in <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">failure analysis entry</a>.</p>
<p>The <b>DEBUG_FLR_PARAM_TYPE</b> enumeration is also called the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration.</p>


## -syntax

````
typedef enum _DEBUG_FLR_PARAM_TYPE { 
  DEBUG_FLR_INVALID        = 0,
  DEBUG_FLR_RESERVED,
  DEBUG_FLR_DRIVER_OBJECT,
  ...,
  DEBUG_FLR_MASK_ALL       = 0xFFFFFFFF
} DEBUG_FLR_PARAM_TYPE;
````


## -enum-fields
<dl>

### -field <a id="DEBUG_FLR_INVALID"></a><a id="debug_flr_invalid"></a><b>DEBUG_FLR_INVALID</b>

<dd></dd>

### -field <a id="DEBUG_FLR_RESERVED"></a><a id="debug_flr_reserved"></a><b>DEBUG_FLR_RESERVED</b>

<dd></dd>

### -field <a id="DEBUG_FLR_DRIVER_OBJECT"></a><a id="debug_flr_driver_object"></a><b>DEBUG_FLR_DRIVER_OBJECT</b>

<dd></dd>

### -field <a id="..."></a><b>...</b>

<dd></dd>

### -field <a id="DEBUG_FLR_MASK_ALL"></a><a id="debug_flr_mask_all"></a><b>DEBUG_FLR_MASK_ALL</b>

<dd></dd>
</dl>

## -remarks
<p>There are several hundred tags in the <b>DEBUG_FLR_PARAM_TYPE</b> enumeration. You can see all the tags in the extsfns.h header file, which in the Debugging Tools for Windows package.</p>

<p>The tags are grouped by categories, with the first entry of a new category being assigned an explicit value.  For example, the tags that are used for structured data begin with DEBUG_FLR_STACK = 0x200000.</p>

<p>For more information about tags, see <a href="debugger.writing_an_analysis_extension_to_extend__analyze#failure_analysis_entries_tags_and_data_types#failure_analysis_entries_tags_and_data_types">Failure Analysis Entries, Tags, and Data Types</a></p>

<p>There are several hundred tags in the <b>DEBUG_FLR_PARAM_TYPE</b> enumeration. You can see all the tags in the extsfns.h header file, which in the Debugging Tools for Windows package.</p>

<p>The tags are grouped by categories, with the first entry of a new category being assigned an explicit value.  For example, the tags that are used for structured data begin with DEBUG_FLR_STACK = 0x200000.</p>

<p>For more information about tags, see <a href="debugger.writing_an_analysis_extension_to_extend__analyze#failure_analysis_entries_tags_and_data_types#failure_analysis_entries_tags_and_data_types">Failure Analysis Entries, Tags, and Data Types</a></p>

<p>There are several hundred tags in the <b>DEBUG_FLR_PARAM_TYPE</b> enumeration. You can see all the tags in the extsfns.h header file, which in the Debugging Tools for Windows package.</p>

<p>The tags are grouped by categories, with the first entry of a new category being assigned an explicit value.  For example, the tags that are used for structured data begin with DEBUG_FLR_STACK = 0x200000.</p>

<p>For more information about tags, see <a href="debugger.writing_an_analysis_extension_to_extend__analyze#failure_analysis_entries_tags_and_data_types#failure_analysis_entries_tags_and_data_types">Failure Analysis Entries, Tags, and Data Types</a></p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Extsfns.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj991807">Failure Analysis Entries</a>
</dt>
<dt>
<a href="debugger.fa_tag">FA_TAG enumeration</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_FLR_PARAM_TYPE enumeration%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>