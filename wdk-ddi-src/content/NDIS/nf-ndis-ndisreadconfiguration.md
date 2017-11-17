---
UID: NF.ndis.NdisReadConfiguration
title: NdisReadConfiguration
author: windows-driver-content
description: The NdisReadConfiguration function returns the value of a named entry of the specified type from the registry, given the handle to an open registry key.
old-location: netvista\ndisreadconfiguration.htm
ms.assetid: 74560229-9e97-40b9-961c-6bf726586e27
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   NdisReadConfiguration (NDIS
   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   NdisReadConfiguration (NDIS
   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisReadConfiguration
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: NdisReadConfiguration
req.iface: 
---

# NdisReadConfiguration function



## -description
<p>The 
  <b>NdisReadConfiguration</b> function returns
  the value of a named entry of the specified type from the registry, given the handle to an open registry
  key. This function must be invoked serially with respect to itself and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a> function.</p>


## -syntax

````
VOID NdisReadConfiguration(
  _Out_ PNDIS_STATUS                  Status,
  _Out_ PNDIS_CONFIGURATION_PARAMETER *ParameterValue,
  _In_  NDIS_HANDLE                   ConfigurationHandle,
  _In_  PNDIS_STRING                  Keyword,
  _In_  NDIS_PARAMETER_TYPE           ParameterType
);
````


## -parameters
<dl>

### -param <i>Status</i> [out]

<dd>
<p>A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_STATUS_SUCCESS"></a><a id="ndis_status_success"></a><dl>

### -param <b>NDIS_STATUS_SUCCESS</b>

</dl>
</td>
<td width="60%">
<p>The buffer at 
       <i>ParameterValue</i> contains the returned configuration information.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_STATUS_RESOURCES"></a><a id="ndis_status_resources"></a><dl>

### -param <b>NDIS_STATUS_RESOURCES</b>

</dl>
</td>
<td width="60%">
<p>NDIS could not allocate resources, usually enough memory, to return the requested
       information.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_STATUS_FAILURE"></a><a id="ndis_status_failure"></a><dl>

### -param <b>NDIS_STATUS_FAILURE</b>

</dl>
</td>
<td width="60%">
<p>The requested information could not be found under the opened registry key designated by the 
       <i>ConfigurationHandle</i>.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>ParameterValue</i> [out]

<dd>
<p>A pointer to a memory location where NDIS supplies a pointer to an 
     <a href="https://msdn.microsoft.com/80250799-4263-43c0-85d5-f1c1c1fb0bae">
     NDIS_CONFIGURATION_PARAMETER</a> structure if the call to 
     <b>NdisReadConfiguration</b> is
     successful. NDIS allocates memory for the 
     <b>
     NDIS_CONFIGURATION_PARAMETER</b> structure.</p>
</dd>

### -param <i>ConfigurationHandle</i> [in]

<dd>
<p>The handle to a registry key that was returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>, 
     <a href="https://msdn.microsoft.com/e405853a-cf25-4214-82a9-bc3d76334413">
     NdisOpenConfigurationKeyByIndex</a>, or 
     <a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
     NdisOpenConfigurationKeyByName</a> function.</p>
</dd>

### -param <i>Keyword</i> [in]

<dd>
<p>A pointer to a caller-supplied NDIS_STRING type describing a counted string, in the system-default
     character set, specifying the name of the entry under the open registry key for which to return the
     value. 
     </p>
<p>Alternatively, pointer to a caller-supplied NDIS_STRING_CONSTANT specifying one of the following
     predefined entry names along with predefined return values:</p>
<table>
<tr>
<th>Predefined Entry Name</th>
<th>Predefined Return Values</th>
</tr>
<tr>
<td>
<p>ProcessorType</p>
</td>
<td>
<p>
<ul>
<li>NdisProcessorX86</li>
<li>NdisProcessorAmd64</li>
<li>NdisProcessorIA64</li>
<li>NdisProcessorAlpha</li>
</ul> The following are possible only if an old (pre-NDIS 6.0) driver: 
        <ul>
<li>NdisProcessorMips</li>
<li>NdisProcessorPpc</li>
</ul>
</p>
</td>
</tr>
<tr>
<td>
<p>NdisVersion</p>
</td>
<td>
<p>0xMMMMmmmm, where 
        <i>MMMM</i> is the major version and 
        <i>mmmm</i> is the minor version number. For example, 0x00050000 indicates that the highest NDIS
        version supported by the system is major version 5, minor version 0.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param <i>ParameterType</i> [in]

<dd>
<p>The type of the value entry that is specified as one of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a> enumeration values.
     This parameter is ignored in Windows NT and later versions.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>keyword</i> is a synonym for a 
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    <b>NULL</b>.</p>

<p>Every NDIS driver can set up configuration information in the registry for itself using the 
    <b>AddReg</b> directive in its INF file. For example, a protocol driver might store its
    own name as an entry with a preformatted string value that can be passed in calls to the 
    <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
    NdisRegisterProtocolDriver</a> function. For more information, see 
    <a href="netvista.add_registry_sections_in_a_network_inf_file">Add-registry-sections in
    a Network INF File</a>.</p>

<p>Each miniport driver also has associated value entries in the registry. The value entries for any
    particular miniport driver can be device-dependent in nature. For example, a miniport driver might have
    keywords such as *FlowControl, *SpeedDuplex, and *InterruptModeration. The value associated with such an
    NDIS keyword can be either an integer (ULONG-type) or a string (NDIS_STRING-type). For example, the set
    of possible values for the already mentioned *FlowControl entry might be <b>NdisParameterInteger</b> values 0,
    1, 2, or 3, or the equivalents in hexadecimal as <b>NdisParameterHexInteger</b> values.</p>

<p>NdisReadConfiguration buffers and copies the caller-supplied string at 
    <i>Keyword</i> and releases the storage it allocates for this copy before it returns control to the
    caller. The memory it allocates for the 
    <a href="https://msdn.microsoft.com/80250799-4263-43c0-85d5-f1c1c1fb0bae">
    NDIS_CONFIGURATION_PARAMETER</a> structure is freed when the driver releases the ConfigurationHandle
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisReadConfiguration</b> is responsible
    for releasing the buffered string at 
    <i>Keyword</i>.</p>

<p>Note that NDIS does not validate values that a driver reads from the registry. The caller of 
    <b>NdisReadConfiguration</b> must therefore
    not make any assumptions about such values and must validate each value read from the registry. If the
    caller determines that a value is out of bounds, it should use a default value instead.</p>

<p>For more information about setup and installation files, see 
    <a href="devinst.overview_of_device_and_driver_installation">Device Installation
    Overview</a>.</p>

<p>In the configuration registry of Windows 2000 and later versions, an NDIS 
    <i>keyword</i> is a synonym for a 
    <i>value entry name</i>. Such a name is a counted sequence of Unicode characters, terminated with a
    <b>NULL</b>.</p>

<p>Every NDIS driver can set up configuration information in the registry for itself using the 
    <b>AddReg</b> directive in its INF file. For example, a protocol driver might store its
    own name as an entry with a preformatted string value that can be passed in calls to the 
    <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
    NdisRegisterProtocolDriver</a> function. For more information, see 
    <a href="netvista.add_registry_sections_in_a_network_inf_file">Add-registry-sections in
    a Network INF File</a>.</p>

<p>Each miniport driver also has associated value entries in the registry. The value entries for any
    particular miniport driver can be device-dependent in nature. For example, a miniport driver might have
    keywords such as *FlowControl, *SpeedDuplex, and *InterruptModeration. The value associated with such an
    NDIS keyword can be either an integer (ULONG-type) or a string (NDIS_STRING-type). For example, the set
    of possible values for the already mentioned *FlowControl entry might be <b>NdisParameterInteger</b> values 0,
    1, 2, or 3, or the equivalents in hexadecimal as <b>NdisParameterHexInteger</b> values.</p>

<p>NdisReadConfiguration buffers and copies the caller-supplied string at 
    <i>Keyword</i> and releases the storage it allocates for this copy before it returns control to the
    caller. The memory it allocates for the 
    <a href="https://msdn.microsoft.com/80250799-4263-43c0-85d5-f1c1c1fb0bae">
    NDIS_CONFIGURATION_PARAMETER</a> structure is freed when the driver releases the ConfigurationHandle
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a> function.
    The caller of 
    <b>NdisReadConfiguration</b> is responsible
    for releasing the buffered string at 
    <i>Keyword</i>.</p>

<p>Note that NDIS does not validate values that a driver reads from the registry. The caller of 
    <b>NdisReadConfiguration</b> must therefore
    not make any assumptions about such values and must validate each value read from the registry. If the
    caller determines that a value is out of bounds, it should use a default value instead.</p>

<p>For more information about setup and installation files, see 
    <a href="devinst.overview_of_device_and_driver_installation">Device Installation
    Overview</a>.</p>

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
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/598f009b-aec8-4d8f-8b98-061573545109">NdisReadConfiguration (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisReadConfiguration (NDIS
   5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547982">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564868">NDIS_CONFIGURATION_PARAMETER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566740">NDIS_PARAMETER_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8efdcf9f-df8c-4b3b-8b21-11a10a885322">
   NdisAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562604">NdisFreeString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562730">NdisInitAnsiString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562741">NdisInitializeString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562745">NdisInitUnicodeString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e405853a-cf25-4214-82a9-bc3d76334413">
   NdisOpenConfigurationKeyByIndex</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
   NdisOpenConfigurationKeyByName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564512">NdisReadNetworkAddress</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9">
   NdisUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadConfiguration function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>