---
UID: NS.dxva._DXVA_ConfigPictureDecode
title: DXVA_ConfigPictureDecode
author: windows-driver-content
description: The DXVA_ConfigPictureDecode structure is sent by the host decoder to the accelerator to set the configuration for compressed picture decoding.
old-location: display\dxva_configpicturedecode.htm
ms.assetid: b36c2901-33ca-4c76-98d0-8dbe6551226b
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_ConfigPictureDecode
req.alt-loc: dxva.h
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
ms.keywords: DXVA_ConfigPictureDecode, DXVA_ConfigPictureDecode, *LPDXVA_ConfigPictureDecode
req.iface: 
---

# DXVA_ConfigPictureDecode structure



## -description
<p>The DXVA_ConfigPictureDecode structure is sent by the host decoder to the accelerator to set the configuration for compressed picture decoding.</p>


## -syntax

````
typedef struct _DXVA_ConfigPictureDecode {
  DXVA_ConfigQueryOrReplyFunc dwFunction;
  DWORD                       dwReservedBits[3];
  GUID                        guidConfigBitstreamEncryption;
  GUID                        guidConfigMBcontrolEncryption;
  GUID                        guidConfigResidDiffEncryption;
  BYTE                        bConfigBitstreamRaw;
  BYTE                        bConfigMBcontrolRasterOrder;
  BYTE                        bConfigResidDiffHost;
  BYTE                        bConfigSpatialResid8;
  BYTE                        bConfigResid8Subtraction;
  BYTE                        bConfigSpatialHost8or9Clipping;
  BYTE                        bConfigSpatialResidInterleaved;
  BYTE                        bConfigIntraResidUnsigned;
  BYTE                        bConfigResidDiffAccelerator;
  BYTE                        bConfigHostInverseScan;
  BYTE                        bConfigSpecificIDCT;
  BYTE                        bConfig4GroupedCoefs;
} DXVA_ConfigPictureDecode, *LPDXVA_ConfigPictureDecode;
````


## -struct-fields
<dl>

### -field <b>dwFunction</b>

<dd>
<p>Indicates the type of query or response when using probing and locking commands. The most significant 24 bits of <b>dwFunction</b> is the <a href="https://msdn.microsoft.com/bfb1a98e-b9f0-4baa-b486-b2ff33a8bac5">DXVA_ConfigQueryOrReplyFlag</a> variable.</p>
<p>The least significant 4 bits of the <i>DXVA_ConfigQueryOrReplyFlag</i> variable contains status indicators for the query or response being performed.</p>
<p>The least significant 8 bits of <b>dwFunction</b> is the <a href="https://msdn.microsoft.com/6db9fa71-7bc2-4eb6-afcb-b16df48f7e8b">bDXVA_Func variable</a> that, in this case, is equal to 1.</p>
</dd>

### -field <b>dwReservedBits</b>

<dd>
<p>Reserved bits used for packing and alignment. These bits are zero.</p>
</dd>

### -field <b>guidConfigBitstreamEncryption</b>

<dd>
<p>Indicates a GUID associated with the encryption protocol type for bitstream data buffers. The value DXVA_NoEncrypt (a GUID name defined in <i>dxva.h</i>) indicates that encryption is not applied. This is DXVA_NoEncrypt if <b>bConfigBitstreamRaw</b> is zero.</p>
</dd>

### -field <b>guidConfigMBcontrolEncryption</b>

<dd>
<p>Indicates a GUID associated with the encryption protocol type for <a href="https://msdn.microsoft.com/7a416992-04d3-4307-83b3-9fb94c17d60e">macroblock control buffers</a>. The value DXVA_NoEncrypt (a GUID name defined in <i>dxva.h</i>) indicates that encryption is not applied. This is DXVA_NoEncrypt if <b>bConfigBitstreamRaw</b> is 1. </p>
</dd>

### -field <b>guidConfigResidDiffEncryption</b>

<dd>
<p>Indicates a GUID associated with the encryption protocol type for residual difference decoding data buffers (buffers containing spatial-domain data or sets of transform-domain coefficients for accelerator-based <a href="wdkgloss.i#wdkgloss.idct#wdkgloss.idct"><i>IDCT</i></a>). This is DXVA_NoEncrypt if <b>bConfigBitstreamRaw</b> is 1. (DXVA_NoEncrypt is a GUID defined in <i>dxva.h</i> that indicates encryption is not applied.)</p>
</dd>

### -field <b>bConfigBitstreamRaw</b>

<dd>
<p>Contains the bitstream processing indicator. A value of 1 specifies that the picture data will be sent in bitstream buffers as raw bitstream content. A value of zero specifies that picture data will be sent using macroblock control command buffers. </p>
<p>This is zero if <b>bConfigResidDiffHost</b> is 1 or if <b>bConfigResidDiffAccelerator</b> is 1. The value zero is considered the basic level of support. The additional support of level one is preferred. </p>
</dd>

### -field <b>bConfigMBcontrolRasterOrder</b>

<dd>
<p>Specifies whether macroblock control commands are in raster scan order or in arbitrary order. A value of 1 specifies that the macroblock control commands within each macroblock control command buffer are in raster scan order, and a value of zero indicates arbitrary order. Currently, a driver is allowed to restrict support to raster scan order; however, a driver should support both arbitrary and raster scan order.</p>
</dd>

### -field <b>bConfigResidDiffHost</b>

<dd>
<p>Contains the host residual difference configuration (See <a href="https://msdn.microsoft.com/7a416992-04d3-4307-83b3-9fb94c17d60e">Macroblock-Oriented Picture Decoding</a> for more information). A value of 1 specifies that some residual difference decoding data may be sent as blocks in the spatial domain from the host. A value of zero specifies that spatial domain data will not be sent. This member is zero if <b>bConfigBitstreamRaw</b> is 1. It is preferred that an accelerator support both zero and 1.</p>
</dd>

### -field <b>bConfigSpatialResid8</b>

<dd>
<p>Indicates the word size used to represent residual difference spatial-domain blocks for predicted (nonintra) pictures when using host-based residual difference decoding (when <b>bConfigResidDiffHost</b> is equal to 1).</p>
<p>If <b>bConfigSpatialResid8</b> is 1 and <b>bConfigResidDiffHost</b> is 1, the host will send residual difference spatial-domain blocks for nonintra macroblocks using 8-bit signed samples, and for intra macroblocks in predicted (nonintra) pictures in a format depending on <b>bConfigIntraResidUnsigned</b> as follows:</p>
<ul>
<li>
<p>If <b>bConfigIntraResidUnsigned</b> is zero, spatial-domain blocks for intra macroblocks are sent as 8-bit signed integer values relative to a constant reference value of 128.</p>
</li>
<li>
<p>If <b>bConfigIntraResidUnsigned</b> is 1, spatial-domain blocks for intra macroblocks are sent as 8-bit unsigned integer values relative to a constant reference value of zero.</p>
</li>
</ul>
<p>If <b>bConfigSpatialResid8</b> is zero and <b>bConfigResidDiffHost</b> is 1, the host will send residual difference spatial-domain blocks of data for nonintra macroblocks using 16-bit signed samples, and for intra macroblocks in predicted (nonintra) pictures in a format depending on <b>bConfigIntraResidUnsigned</b> as follows:</p>
<ul>
<li>
<p>If <b>bConfigIntraResidUnsigned</b> is zero, spatial domain blocks for intra macroblocks are sent as 16-bit signed integer values relative to a constant reference value of 2<sup>(BPP-1)</sup>, where <i>BPP</i> is the number of bits per sample for the uncompressed video (generally a value of 8).</p>
</li>
<li>
<p>If <b>bConfigIntraResidUnsigned</b> is 1, spatial domain blocks for intra macroblocks are sent as 16-bit unsigned integer values relative to a constant reference value of zero.</p>
</li>
</ul>
<p>The <b>bConfigSpatialResid8</b> member must be zero if <b>bConfigResidDiffHost</b> is zero. There is no preference for one particular value of <b>bConfigSpatialResid8</b> when <b>bConfigResidDiffHost</b> is 1.</p>
<div class="alert"><b>Note</b>    For <a href="wdkgloss.i#wdkgloss.intra_picture#wdkgloss.intra_picture"><i>intra pictures</i></a> with <i>BPP</i> equal to 8, spatial-domain blocks must be sent using 8-bit samples. For intra pictures with <i>BPP</i> greater than 8, spatial-domain blocks must be sent using 16-bit samples. (The <i>BPP</i> variable is the number of bits per sample for the uncompressed video, generally a value of 8.)<p class="note">If <b>bConfigIntraResidUnsigned</b> is zero, these samples are sent as signed integer values relative to a constant reference value of 2<sup>(BPP-1)</sup>. If <b>bConfigIntraResidUnsigned</b> is 1, these samples are sent as unsigned integer values relative to a constant reference value of zero.</p>
</div>
<div> </div>
</dd>

### -field <b>bConfigResid8Subtraction</b>

<dd>
<p>When equal to 1, indicates that 8-bit difference overflow blocks are subtracted rather than added. Must be zero unless <b>bConfigSpatialResid8</b> is 1. The preferred value for an accelerator to support is 1 if <b>bConfigSpatialResid8</b> is 1. The ability to subtract differences rather than to add them allows 8-bit difference decoding to be fully compliant with the full +/-255 range of values required in video decoder specifications. This is because +255 cannot be represented as the addition of two signed 8-bit numbers but any number in the range +/-255 can be represented as the difference between two signed 8-bit numbers (+255 is equal to +127 minus âˆ’128).</p>
</dd>

### -field <b>bConfigSpatialHost8or9Clipping</b>

<dd>
<p>When equal to 1, indicates that spatial-domain blocks for intra macroblocks are clipped to an 8-bit range on the host and that spatial-domain blocks for nonintra macroblocks are clipped to a 9-bit range on the host. A value of zero indicates that no such clipping is performed by the host. Must be zero unless <b>bConfigSpatialResid8</b> is equal to zero and <b>bConfigResidDiffHost</b> is equal to 1. The preferred value for an accelerator to support is zero.</p>
</dd>

### -field <b>bConfigSpatialResidInterleaved</b>

<dd>
<p>When equal to 1, indicates that any spatial-domain residual difference data is sent in a chrominance-interleaved form matching the YUV format chrominance interleaving pattern. Must be zero unless <b>bConfigResidDiffHost</b> is 1 and the YUV format is NV12 or NV21. The preferred value for an accelerator to support is zero.</p>
</dd>

### -field <b>bConfigIntraResidUnsigned</b>

<dd>
<p>Indicates the method of representation of spatial-domain blocks of residual difference data for intra blocks when using host-based difference decoding (when <b>bConfigResidDiffHost</b> is equal to 1).</p>
<p>When <b>bConfigIntraResidUnsigned</b> is equal to zero and <b>bConfigResidDiffHost</b> is equal to 1, spatial-domain residual difference data blocks for intra macroblocks are sent as follows:</p>
<ul>
<li>
<p>In a nonintra picture if <b>bConfigSpatialResid8</b> is zero, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit signed integer values relative to a constant reference value of 2<sup>(BPP-1)</sup>, where <i>BPP</i> is the number of bits per sample for the uncompressed video (generally a value of 8).</p>
</li>
<li>
<p>In a nonintra picture if <b>bConfigSpatialResid8</b> is 1 and in an intra picture if <i>BPP</i> is equal to 8 (regardless of the value of <b>bConfigSpatialResid8</b>), the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit signed integer values relative to a constant reference value of 128.</p>
</li>
</ul>
<p>When <b>bConfigIntraResidUnsigned</b> is equal to 1 and <b>bConfigResidDiffHost</b> is equal to 1, spatial-domain residual difference data blocks for intra macroblocks are sent as follows:</p>
<ul>
<li>
<p>In a nonintra picture if <b>bConfigSpatialResid8</b> is zero, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit unsigned integer values relative to a constant reference value of zero.</p>
</li>
<li>
<p>In a nonintra picture if <b>bConfigSpatialResid8</b> is 1 and in an intra picture if <i>BPP</i> is equal to 8 (regardless of the value of <b>bConfigSpatialResid8</b>), the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit unsigned integer values relative to a constant reference value of zero.</p>
</li>
</ul>
<p>The <b>bConfigIntraResidUnsigned</b> member must be zero unless <b>bConfigResidDiffHost</b> is 1. </p>
<p>The preferred value for an accelerator to support is zero for <b>bConfigIntraResidUnsigned</b>.</p>
</dd>

### -field <b>bConfigResidDiffAccelerator</b>

<dd>
<p>Contains the accelerator residual difference configuration. A value of 1 indicates that transform-domain blocks of coefficient data may be sent from the host for accelerator-based IDCT. A value of zero specifies that accelerator-based IDCT will not be used. If both <b>bConfigResidDiffHost</b> and <b>bConfigResidDiffAccelerator</b> are 1, some residual difference decoding will be done on the host and some on the accelerator, as indicated by macroblock-level control commands. This member must be zero if <b>bConfigBitstreamRaw</b> is 1. </p>
<p>The preferred value for an accelerator to support is 1 for <b>bConfigResidDiffAccelerator</b>.</p>
<p>When <b>bConfigResidDiffAccelerator</b> and <b>bConfigResidDiffHost</b> are equal to 1, residual difference decoding can be shared between the host and accelerator on a macroblock basis. This is considered an even higher level of accelerator capability than when <b>bConfigResidDiffAccelerator</b> is equal to 1 and <b>bConfigResidDiffHost</b> is equal to zero.</p>
</dd>

### -field <b>bConfigHostInverseScan</b>

<dd>
<p>Indicates whether the inverse scan for transform-domain block processing is performed on the host or the accelerator. A value of 1 indicates that the inverse scan for transform-domain block processing will be performed on the host, and absolute indices will be sent instead for any transform coefficients. A value of zero indicates that inverse scan will be performed on the accelerator. This member must be zero if <b>bConfigResidDiffAccelerator</b> is zero or if <b>bConfig4GroupedCoefs</b> is 1.</p>
<p>The preferred value for an accelerator to support is 1 if <b>bConfigResidDiffAccelerator</b> is 1.</p>
</dd>

### -field <b>bConfigSpecificIDCT</b>

<dd>
<p>Indicates the use of a specific <a href="wdkgloss.i#wdkgloss.idct#wdkgloss.idct"><i>IDCT</i></a> method for off-host IDCT. A value of 1 indicates use of the IDCT specified in Annex W of ITU-T Recommendation H.263. A value of zero indicates that any compliant IDCT can be used for off-host IDCT. (Values other than zero and 1 are reserved for future use.)</p>
<p>This member must be zero if <b>bConfigResidDiffAccelerator</b> is zero (simply indicating host-based residual difference decoding).</p>
<div class="alert"><b>Note</b>    Annex W of ITU-T Recommendation H.263 does not comply with the IDCT requirements of MPEG-2 corrigendum 2 and thus <b>bConfigSpecificIDCT</b> must not be one for use with MPEG-2 video. </div>
<div> </div>
</dd>

### -field <b>bConfig4GroupedCoefs</b>

<dd>
<p>A value of 1 indicates that transform coefficients for off-host IDCT will be sent using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564053">DXVA_TCoef4Group</a> structure rather than the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564060">DXVA_TCoefSingle</a> structure. This is zero if <b>bConfigResidDiffAccelerator</b> is zero or if <b>bConfigHostInverseScan</b> is 1.</p>
<p>The preferred value for an accelerator to support is zero if <b>bConfigResidDiffAccelerator</b> is 1.</p>
</dd>
</dl>

## -remarks
<p>For some types of bitstreams, forcing macroblock control commands within each macroblock control command buffer to be in raster order either greatly increases the number of required buffers that must be processed or requires host reordering of the control information. Support of arbitrary order can thus be advantageous for the decoding process. For example, H.261 CIF-resolution decoding can require 36 macroblock control buffers per picture if raster scan order is necessary within each buffer (H.263 Annex K's arbitrary slice ordering and rectangular slice modes have more severe repercussions, possibly requiring an extremely large number of buffers.)</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564053">DXVA_TCoef4Group</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564060">DXVA_TCoefSingle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563983">DXVA_MBctrl_I_HostResidDiff_1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563989">DXVA_MBctrl_I_OffHostIDCT_1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563993">DXVA_MBctrl_P_HostResidDiff_1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563997">DXVA_MBctrl_P_OffHostIDCT_1</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ConfigPictureDecode structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>