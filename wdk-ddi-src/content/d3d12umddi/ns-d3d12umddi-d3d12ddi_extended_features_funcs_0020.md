---
UID: NS:d3d12umddi.D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
title: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
author: windows-driver-content
description: This structure contains device functions for extended features in video.
old-location: display\d3d12ddi_extended_features_funcs_0020.htm
old-project: display
ms.assetid: 36AAD6F2-3220-4F9A-AA10-BA8D87948D09
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020, D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure [Display Devices], d3d12umddi/D3D12DDI_EXTENDED_FEATURES_FUNCS_0020, display.d3d12ddi_extended_features_funcs_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
---

# D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure


## -description


This structure contains device functions for extended features in  video.


## -struct-fields




### -field pfnGetSupportedExtendedFeatures

A pointer for a callback function to get supported extended features.


### -field pfnGetSupportedExtendedFeatureVersions

A pointer for a callback function to get the supported versions of extended features.


### -field pfnEnableExtendedFeature

A pointer for a callback function to enable an extended feature.

