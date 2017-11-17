---
UID: NS.compstui._CPSUICBPARAM
title: CPSUICBPARAM
author: windows-driver-content
description: The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions.
old-location: print\cpsuicbparam.htm
ms.assetid: b5545efa-6cb4-41d0-9338-be9a269fa193
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: print
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CPSUICBPARAM
req.alt-loc: compstui.h
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
ms.keywords: CPSUICBPARAM, CPSUICBPARAM, *PCPSUICBPARAM
req.iface: 
---

# CPSUICBPARAM structure



## -description
<p>The CPSUICBPARAM structure is used as the input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564313">_CPSUICALLBACK</a>-typed callback functions.</p>


## -syntax

````
typedef struct _CPSUICBPARAM {
  WORD      cbSize;
  WORD      Reason;
  HWND      hDlg;
  POPTITEM  pOptItem;
  WORD      cOptItem;
  WORD      Flags;
  POPTITEM  pCurItem;
  union {
    LONG   OldSel;
    LPTSTR pOldSel;
  };
  ULONG_PTR UserData;
  ULONG_PTR Result;
} CPSUICBPARAM, *PCPSUICBPARAM;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd>
<p>CPSUI-supplied size, in bytes, of the CPSUICBPARAM structure.</p>
</dd>

### -field <b>Reason</b>

<dd>
<p>CPSUI-supplied value indicating the reason it is calling the callback function. This can be one of the following values:</p>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_ABOUT"></a><a id="cpsuicb_reason_about"></a>CPSUICB_REASON_ABOUT

<dd>
<p>The user has clicked on the page's <b>About</b> button, and the application previously set the CPSUIF_ABOUT_CALLBACK flag in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure. CPSUI sets <i>pCurItem</i> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <b>COMPROPSHEETUI</b> structure.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_APPLYNOW"></a><a id="cpsuicb_reason_applynow"></a>CPSUICB_REASON_APPLYNOW

<dd>
<p>The user has clicked on the page's <b>Apply</b> or <b>OK</b> button, and CPSUI has received a PSN_APPLY notification message (described in the Microsoft Windows SDK documentation). CPSUI sets <b>pCurItem</b> to point to the option to which <b>pOptItem</b> points. It also sets <b>OldSel</b> to minus one to indicate that all valid changed option values should be applied now.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_DLGPROC"></a><a id="cpsuicb_reason_dlgproc"></a>CPSUICB_REASON_DLGPROC

<dd>
<p>The option identified by <b>pCurItem</b> is a push button (<a href="https://msdn.microsoft.com/library/windows/hardware/ff562844">TVOT_PUSHBUTTON</a> option type), and the user has clicked on the button.</p>
<p>The push button option's OPTPARAM <b>Style</b> field is set to PUSHBUTTON_TYPE_DLGPROC.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_ECB_CHANGED"></a><a id="cpsuicb_reason_ecb_changed"></a>CPSUICB_REASON_ECB_CHANGED

<dd>
<p>The option identified by <b>pCurItem</b> is an extended check box, and the user has changed the box's state.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_EXTPUSH"></a><a id="cpsuicb_reason_extpush"></a>CPSUICB_REASON_EXTPUSH

<dd>
<p>The option identified by <b>pCurItem</b> is an extended push button, and the user has clicked on the button.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_ITEMS_REVERTED"></a><a id="cpsuicb_reason_items_reverted"></a>CPSUICB_REASON_ITEMS_REVERTED

<dd>
<p>The user clicked on the page's <b>Undo</b> button, and CPSUI has reverted all selections to their original values.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_KILLACTIVE"></a><a id="cpsuicb_reason_killactive"></a>CPSUICB_REASON_KILLACTIVE

<dd>
<p>The property sheet page is about to lose activation, and CPSUI has received a PSN_KILLACTIVE notification message (described in the Windows SDK documentation). CPSUI sets <b>pCurItem</b> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_OPTITEM_SETFOCUS"></a><a id="cpsuicb_reason_optitem_setfocus"></a>CPSUICB_REASON_OPTITEM_SETFOCUS

<dd>
<p>The option identified by <b>pCurItem</b> has received input focus.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_PUSHBUTTON"></a><a id="cpsuicb_reason_pushbutton"></a>CPSUICB_REASON_PUSHBUTTON

<dd>
<p>The option identified by <b>pCurItem</b> is a push button (<a href="https://msdn.microsoft.com/library/windows/hardware/ff562844">TVOT_PUSHBUTTON</a> option type), and the user has clicked on the button.</p>
<p>The push button item's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559660">OPTPARAM</a> <b>Style</b>  field is set to PUSHBUTTON_TYPE_CALLBACK.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_SEL_CHANGED"></a><a id="cpsuicb_reason_sel_changed"></a>CPSUICB_REASON_SEL_CHANGED

<dd>
<p>The user has changed the selected value for the option pointed to by <b>pCurItem</b>.</p>
</dd>
</dl>
<p></p>
<dl>

### -field <a id="CPSUICB_REASON_SETACTIVE"></a><a id="cpsuicb_reason_setactive"></a>CPSUICB_REASON_SETACTIVE

<dd>
<p>The property sheet page is about to become active, and CPSUI has received a PSN_SETACTIVE notification message (described in the Windows SDK documentation). CPSUI sets <b>pCurItem</b> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.</p>
</dd>
</dl>
</dd>

### -field <b>hDlg</b>

<dd>
<p>CPSUI-supplied handle to the currently active dialog box.</p>
</dd>

### -field <b>pOptItem</b>

<dd>
<p>CPSUI-supplied pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559656">OPTITEM</a> structures. This is the same pointer that the application previously supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.</p>
</dd>

### -field <b>cOptItem</b>

<dd>
<p>CPSUI-supplied number of OPTITEM structures in the array pointed to by <b>pOptItem</b>. This is the same number that the application previously supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>CPSUI-supplied flags. This is the same set of flags that the application previously supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.</p>
</dd>

### -field <b>pCurItem</b>

<dd>
<p>CPSUI-supplied pointer to a member of the OPTITEM array pointed to by <b>pOptItem</b>. This array member represents the "current" option, which is the one for which the callback function was called.</p>
</dd>

### -field <b>OldSel</b>

<dd>
<p>If the <b>Reason</b> member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the <b>OldSel</b>/<b>pOldSel</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559656">OPTITEM</a> structure pointed to by <b>pCurItem</b>.</p>
<p>For all other <b>Reason</b> values, the contents of this union should be ignored.</p>
</dd>

### -field <b>pOldSel</b>

<dd>
<p>If the <b>Reason</b> member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the <b>OldSel</b>/<b>pOldSel</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559656">OPTITEM</a> structure pointed to by <b>pCurItem</b>.</p>
<p>For all other <b>Reason</b> values, the contents of this union should be ignored.</p>
</dd>

### -field <b>UserData</b>

<dd>
<p>CPSUI-supplied user data. This is the same value that the application previously supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.</p>
</dd>

### -field <b>Result</b>

<dd>
<p>Result value supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564313">_CPSUICALLBACK</a>-typed callback function. By default, CPSUI sets this value to CPSUI_OK. After the callback function returns, CPSUI calls its <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function with a function code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547087">CPSFUNC_SET_RESULT</a>, supplying the <b>Reason</b> member contents as the result value.</p>
<p>This member is used only if the <b>Reason</b> member is CPSUICB_REASON_APPLYNOW and the callback function does not return CPSUI_ACTION_NO_APPLY_EXIT.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Compstui.h (include Compstui.h)</dt>
</dl>
</td>
</tr>
</table>