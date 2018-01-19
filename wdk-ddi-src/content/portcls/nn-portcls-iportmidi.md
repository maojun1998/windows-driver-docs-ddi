---
UID : NN:portcls.IPortMidi
title : IPortMidi
author : windows-driver-content
description : The IPortMidi interface is the MIDI port driver's primary interface.
old-location : audio\iportmidi.htm
old-project : audio
ms.assetid : e5403377-fd24-4fd5-8158-194f30238c44
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PcUnregisterIoTimeout
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPortMidi
req.alt-loc : portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Portcls.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortMidi interface

The <code>IPortMidi</code> interface is the MIDI port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a> object. An adapter driver creates an <code>IPortMidi</code> object by calling <a href="..\portcls\nf-portcls-pcnewport.md">PcNewPort</a> and specifying REFIID <b>IID_IPortMidi</b>. <code>IPortMidi</code> inherits from the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportMidi</b> object to an <code>IPortMidi</code> object. The PortCls system driver registers this pair with the system as a MIDI filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).

## Methods

<p>The <b>IPortMidi</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IPortMidi.Notify](nf-portcls-iportmidi-notify.md) | The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR). |
| [portcls.IPortMidi.RegisterServiceGroup](nf-portcls-iportmidi-registerservicegroup.md) | The RegisterServiceGroup method registers the service group to be used for the IPortMidi::Notify method. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **DLL** |  |