---
UID: NF.bdasup.BdaFilterFactoryUpdateCacheData
title: BdaFilterFactoryUpdateCacheData function
author: windows-driver-content
description: The BdaFilterFactoryUpdateCacheData function updates the pin data cache for an instance of a filter.
old-location: stream\bdafilterfactoryupdatecachedata.htm
old-project: stream
ms.assetid: c4b8220a-bd54-4e41-a00e-3750a3f03cae
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: BdaFilterFactoryUpdateCacheData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BdaFilterFactoryUpdateCacheData
req.alt-loc: Bdasup.lib,Bdasup.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# BdaFilterFactoryUpdateCacheData function



## -description
The<b> BdaFilterFactoryUpdateCacheData</b> function updates the pin data cache for an instance of a filter.


## -syntax

````
NTSTATUS BdaFilterFactoryUpdateCacheData(
  _In_           PKSFILTERFACTORY    pFilterFactory,
  _In_opt_ const KSFILTER_DESCRIPTOR *pFilterDescriptor
);
````


## -parameters

### -param pFilterFactory [in]

Points to the <a href="stream.ksfilterfactory">KSFILTERFACTORY</a> for which to update the pin data cache.

### -param pFilterDescriptor [in, optional]

Points to an optional <a href="stream.ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> for which the pin data cache will be updated. If <b>NULL</b>, <i>pFilterFactory</i>'s descriptor is used instead. This parameter enables dynamic pin creation, that is, pin creation that occurs after a filter's create dispatch routine completes.

## -returns
Returns STATUS_SUCCESS or an appropriate error code. Returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.

## -remarks
A BDA minidriver calls the <b>BdaFilterFactoryUpdateCacheData</b> function to update the pin data cache for all pins specified at <i>pFilterDescriptor</i>. In this call, the BDA minidriver typically passes the <b>pFilterDescriptor</b> member of a <a href="stream.bda_filter_template">BDA_FILTER_TEMPLATE</a> structure that describes the template topology for the BDA filter to <i>pFilterDescriptor</i>. If <i>pFilterDescriptor</i> is <b>NULL</b>, the cached information will be updated for all pin factories specified at <i>pFilterFactory</i>'s KSFILTER_DESCRIPTOR member. For information about the pin data cache, see <a href="https://msdn.microsoft.com/1e6a973b-32d2-4ac2-9cd6-f4d3c329cecf">Caching Pin Information for DirectShow</a>. 

The <a href="stream.ksregisterfilterwithnokspins">KsRegisterFilterWithNoKSPins</a> function provides similar functionality but only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bdasup.h (include Bdasup.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Bdasup.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.bda_filter_template">BDA_FILTER_TEMPLATE</a>
</dt>
<dt>
<a href="stream.ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>
</dt>
<dt>
<a href="stream.ksfilterfactory">KSFILTERFACTORY</a>
</dt>
<dt>
<a href="stream.ksregisterfilterwithnokspins">KsRegisterFilterWithNoKSPins</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaFilterFactoryUpdateCacheData function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>