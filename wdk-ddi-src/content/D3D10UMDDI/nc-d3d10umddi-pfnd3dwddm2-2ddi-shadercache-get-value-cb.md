---
UID: NC.d3d10umddi.PFND3DWDDM2_2DDI_SHADERCACHE_GET_VALUE_CB
title: PFND3DWDDM2_2DDI_SHADERCACHE_GET_VALUE_CB
author: windows-driver-content
description: 
ms.assetid: 84fabe63-3537-47ff-9c0d-4eabc2eddc02
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

# PFND3DWDDM2_2DDI_SHADERCACHE_GET_VALUE_CB callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3DWDDM2_2DDI_SHADERCACHE_GET_VALUE_CB Pfnd3dwddm22DdiShadercacheGetValueCb; 

// Definition

HRESULT Pfnd3dwddm22DdiShadercacheGetValueCb 
(
	D3DWDDM2_2DDI_HRTCACHESESSION hCacheSession
	 const D3DWDDM2_2DDI_SHADERCACHE_HASH *pPrecomputedHash
	 const void *pKey
	SIZE_T KeyLen
	 void *pValue
	SIZE_T *pValueLen
)
{...}

PFND3DWDDM2_2DDI_SHADERCACHE_GET_VALUE_CB 


```

## -parameters

### -param hCacheSession: 
### -param *pPrecomputedHash: 
### -param *pKey: 
### -param KeyLen: 
### -param *pValue: 
### -param *pValueLen: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also