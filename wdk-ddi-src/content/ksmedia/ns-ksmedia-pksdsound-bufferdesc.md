---
UID: NS.ksmedia.PKSDSOUND_BUFFERDESC
title: PKSDSOUND_BUFFERDESC
author: windows-driver-content
description: The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer.
old-location: audio\ksdsound_bufferdesc.htm
ms.assetid: 95b2f2ff-b98f-4210-9a4f-898573679aa7
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: audio
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSDSOUND_BUFFERDESC
req.alt-loc: ksmedia.h
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
ms.keywords: PKSDSOUND_BUFFERDESC, KSDSOUND_BUFFERDESC, *PKSDSOUND_BUFFERDESC
req.iface: 
---

# PKSDSOUND_BUFFERDESC structure



## -description
<p>The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer.</p>


## -syntax

````
typedef struct {
  ULONG        Flags;
  ULONG        Control;
  WAVEFORMATEX WaveFormatEx;
} KSDSOUND_BUFFERDESC, *PKSDSOUND_BUFFERDESC;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>Specifies the buffer configuration. This member can be set to the bitwise OR of one or more of the following flag bits:</p>
<p></p>
<dl>

### -field <a id="KSDSOUND_BUFFER_PRIMARY"></a><a id="ksdsound_buffer_primary"></a>KSDSOUND_BUFFER_PRIMARY

<dd>
<p>Indicates that the buffer is a primary sound buffer (the buffer the user hears when a game is playing).</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_STATIC"></a><a id="ksdsound_buffer_static"></a>KSDSOUND_BUFFER_STATIC

<dd>
<p>Indicates that the buffer will be used for static sound data.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_LOCHARDWARE"></a><a id="ksdsound_buffer_lochardware"></a>KSDSOUND_BUFFER_LOCHARDWARE

<dd>
<p>Forces the buffer to use hardware mixing.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_LOCSOFTWARE"></a><a id="ksdsound_buffer_locsoftware"></a>KSDSOUND_BUFFER_LOCSOFTWARE

<dd>
<p>Forces the buffer to be stored in system memory and use software mixing.</p>
</dd>
</dl>
</dd>

### -field <b>Control</b>

<dd>
<p>Specifies the capabilities of the buffer. The capabilities of a buffer are represented by a set of control flags. This member can be set to the bitwise OR of one or more of the following flag bits:</p>
<p></p>
<dl>

### -field <a id="KSDSOUND_BUFFER_CTRL_3D"></a><a id="ksdsound_buffer_ctrl_3d"></a>KSDSOUND_BUFFER_CTRL_3D

<dd>
<p>Indicates that the buffer is either a primary buffer or a secondary buffer with 3D-control capability. If this bit is set, the KS pin representing the buffer implements a 3D node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>). If the KSDSOUND_BUFFER_CTRL_HRTF_3D bit is set, the 3D node supports the optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a> property set.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_CTRL_FREQUENCY"></a><a id="ksdsound_buffer_ctrl_frequency"></a>KSDSOUND_BUFFER_CTRL_FREQUENCY

<dd>
<p>Indicates that the buffer has frequency-control capability. If this bit is set, the pin representing the buffer implements a sample-rate conversion (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537190">KSNODETYPE_SRC</a>) node.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_CTRL_HRTF_3D"></a><a id="ksdsound_buffer_ctrl_hrtf_3d"></a>KSDSOUND_BUFFER_CTRL_HRTF_3D

<dd>
<p>Indicates that the buffer uses a head-related transfer function (HRTF) for 3D control. If this bit is set, then the KSDSOUND_BUFFER_CTRL_3D bit must also be set.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_CTRL_PAN"></a><a id="ksdsound_buffer_ctrl_pan"></a>KSDSOUND_BUFFER_CTRL_PAN

<dd>
<p>Indicates that the buffer has pan-control capability. If this bit is set, the pin representing the buffer implements a volume node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>) to control panning. For more information, see <a href="NULL">DirectSound Node-Ordering Requirements</a>.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_CTRL_VOLUME"></a><a id="ksdsound_buffer_ctrl_volume"></a>KSDSOUND_BUFFER_CTRL_VOLUME

<dd>
<p>Indicates that the buffer has volume-control capability. If this bit is set, the pin representing the buffer implements a volume node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>) to control the stream's volume level.</p>
</dd>

### -field <a id="KSDSOUND_BUFFER_CTRL_POSITIONNOTIFY"></a><a id="ksdsound_buffer_ctrl_positionnotify"></a>KSDSOUND_BUFFER_CTRL_POSITIONNOTIFY

<dd>
<p>Indicates that the buffer has position-notification capability. If this bit is set, the pin representing the buffer supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a> property.</p>
</dd>
</dl>
</dd>

### -field <b>WaveFormatEx</b>

<dd>
<p>Specifies the wave-data format of the buffer. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>.</p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537094">KSDATAFORMAT_DSOUND</a> structure contains a <b>BufferDesc</b> member that is a KSDSOUND_BUFFERDESC structure.</p>

<p>Note that the <b>WaveFormatEx</b> member of the KSDSOUND_BUFFERDESC structure can be extended to include additional format information (for example, a channel configuration mask). For details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538802">WAVEFORMATEXTENSIBLE</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537094">KSDATAFORMAT_DSOUND</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537190">KSNODETYPE_SRC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538799">WAVEFORMATEX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538802">WAVEFORMATEXTENSIBLE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDSOUND_BUFFERDESC structure%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>