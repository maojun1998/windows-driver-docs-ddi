---
UID: NC.d3d10umddi.PFND3DWDDM2_0DDI_CALCPRIVATERENDERTARGETVIEWSIZE
title: PFND3DWDDM2_0DDI_CALCPRIVATERENDERTARGETVIEWSIZE
author: windows-driver-content
description: 
ms.assetid: a74c8e86-5edb-4b74-a516-95290cd5d241
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

# PFND3DWDDM2_0DDI_CALCPRIVATERENDERTARGETVIEWSIZE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3DWDDM2_0DDI_CALCPRIVATERENDERTARGETVIEWSIZE Pfnd3dwddm20DdiCalcprivaterendertargetviewsize; 

// Definition

SIZE_T Pfnd3dwddm20DdiCalcprivaterendertargetviewsize 
(
	 D3D10DDI_HDEVICE
	CONST D3DWDDM2_0DDIARG_CREATERENDERTARGETVIEW *
)
{...}

PFND3DWDDM2_0DDI_CALCPRIVATERENDERTARGETVIEWSIZE 


```

## -parameters

### -param D3D10DDI_HDEVICE: 
### -param *: 



## -returns

Returns SIZE_T that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also