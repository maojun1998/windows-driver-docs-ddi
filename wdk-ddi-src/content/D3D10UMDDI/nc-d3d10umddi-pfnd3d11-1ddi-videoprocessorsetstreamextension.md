---
UID: NC.d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION
author: windows-driver-content
description: 
ms.assetid: 4b0e23c4-5014-40ca-af0a-ca509bb609aa
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.alt-api:
req.alt-loc:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION Pfnd3d111DdiVideoprocessorsetstreamextension; 

// Definition

HRESULT Pfnd3d111DdiVideoprocessorsetstreamextension 
(
	 D3D10DDI_HDEVICE
	 D3D11_1DDI_HVIDEOPROCESSOR
	 UINT
	CONST GUID *
	 UINT
	 void *
)
{...}

PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMEXTENSION 


```

## -parameters

### -param D3D10DDI_HDEVICE: 
### -param D3D11_1DDI_HVIDEOPROCESSOR: 
### -param UINT: 
### -param *: 
### -param UINT: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also