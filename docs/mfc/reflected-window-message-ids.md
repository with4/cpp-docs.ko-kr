---
title: "리플렉션된 창 메시지 ID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OCM_CTLCOLORBTN"
  - "OCM_PARENTNOTIFY"
  - "OCM_VKEYTOITEM"
  - "OCM_CTLCOLORSTATIC"
  - "OCM_HSCROLL"
  - "OCM_CHARTOITEM"
  - "OCM_DRAWITEM"
  - "OCM_MEASUREITEM"
  - "OCM_COMPAREITEM"
  - "OCM_COMMAND"
  - "OCM_NOTIFY"
  - "OCM_CTLCOLORMSGBOX"
  - "OCM_DELETEITEM"
  - "OCM_CTLCOLORLISTBOX"
  - "OCM_CTLCOLORDLG"
  - "OCM_CTLCOLOREDIT"
  - "OCM_CTLCOLORSCROLLBAR"
  - "OCM_VSCROLL"
  - "OCM_CTLCOLOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지, 리플렉트됨"
  - "OCM_ 메시지"
  - "OCM_CHARTOITEM 메시지"
  - "OCM_COMMAND 메시지"
  - "OCM_COMPAREITEM 메시지"
  - "OCM_CTLCOLOR 메시지"
  - "OCM_CTLCOLORBTN 메시지"
  - "OCM_CTLCOLORDLG 메시지"
  - "OCM_CTLCOLOREDIT 메시지"
  - "OCM_CTLCOLORLISTBOX 메시지"
  - "OCM_CTLCOLORMSGBOX 메시지"
  - "OCM_CTLCOLORSCROLLBAR 메시지"
  - "OCM_CTLCOLORSTATIC 메시지"
  - "OCM_DELETEITEM 메시지"
  - "OCM_DRAWITEM 메시지"
  - "OCM_HSCROLL 메시지"
  - "OCM_MEASUREITEM 메시지"
  - "OCM_NOTIFY 메시지"
  - "OCM_PARENTNOTIFY 메시지"
  - "OCM_VKEYTOITEM 메시지"
  - "OCM_VSCROLL 메시지"
  - "리플렉트된 메시지"
  - "리플렉트된 메시지, 창 메시지 ID"
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 리플렉션된 창 메시지 ID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A quick way to create an ActiveX control, or other specialized control, is to subclass a window.  For more information, see [MFC ActiveX Controls: Subclassing a Windows Control](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 To prevent the control's container from receiving the window messages sent by a subclassed Windows control, [COleControl](../mfc/reference/colecontrol-class.md) creates a "reflector" window to intercept certain window messages and send them back to the control.  The control, in its window procedure, can then process these reflected messages by taking actions appropriate for an ActiveX control.  
  
 The following table shows the messages that are intercepted and the corresponding messages that the reflector window sends.  
  
|Message sent by the control|Message reflected to the control|  
|---------------------------------|--------------------------------------|  
|[\<caps:sentence id\="tgt8" sentenceid\="873e43d4b95944ef6a24e5ce86283a86" class\="tgtSentence"\>WM\_COMMAND\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms647591)|**OCM\_COMMAND**|  
|[\<caps:sentence id\="tgt10" sentenceid\="4c05f2ab21ae1d3135515bcc85612c15" class\="tgtSentence"\>WM\_CTLCOLORBTN\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb761849)|**OCM\_CTLCOLORBTN**|  
|[\<caps:sentence id\="tgt12" sentenceid\="e7bee49a92d5957960a50078a6c4ff10" class\="tgtSentence"\>WM\_CTLCOLOREDIT\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb761691)|**OCM\_CTLCOLOREDIT**|  
|[\<caps:sentence id\="tgt14" sentenceid\="4e7d61c9b6e22695496cf799f4174d9f" class\="tgtSentence"\>WM\_CTLCOLORDLG\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms645417)|**OCM\_CTLCOLORDLG**|  
|[\<caps:sentence id\="tgt16" sentenceid\="b5346b7e4f669cf080415efd51991c0b" class\="tgtSentence"\>WM\_CTLCOLORLISTBOX\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb761360)|**OCM\_CTLCOLORLISTBOX**|  
|[\<caps:sentence id\="tgt18" sentenceid\="f54bf5423a419738db0a4fc1a27e71ff" class\="tgtSentence"\>WM\_CTLCOLORSCROLLBAR\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb787573)|**OCM\_CTLCOLORSCROLLBAR**|  
|[\<caps:sentence id\="tgt20" sentenceid\="306fe5385a2d130a1af7eeaae7b7a410" class\="tgtSentence"\>WM\_CTLCOLORSTATIC\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb787524)|**OCM\_CTLCOLORSTATIC**|  
|[\<caps:sentence id\="tgt22" sentenceid\="52a902695a63460a61e98eb25c7aaac8" class\="tgtSentence"\>WM\_DRAWITEM\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb775923)|**OCM\_DRAWITEM**|  
|[\<caps:sentence id\="tgt24" sentenceid\="1649d347836eae1c6da98a2558f21bca" class\="tgtSentence"\>WM\_MEASUREITEM\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb775925)|**OCM\_MEASUREITEM**|  
|[\<caps:sentence id\="tgt26" sentenceid\="b69690f0bfa93c77a0c3077dbe5df0a0" class\="tgtSentence"\>WM\_DELETEITEM\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb761362)|**OCM\_DELETEITEM**|  
|[\<caps:sentence id\="tgt28" sentenceid\="dabc6d41d06da731f6ffbd80a7be9c47" class\="tgtSentence"\>WM\_VKEYTOITEM\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb761364)|**OCM\_VKEYTOITEM**|  
|[\<caps:sentence id\="tgt30" sentenceid\="bbc462c9e39eb6780c8c68e9bebdcf3f" class\="tgtSentence"\>WM\_CHARTOITEM\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb761358)|**OCM\_CHARTOITEM**|  
|[\<caps:sentence id\="tgt32" sentenceid\="a27395293112eab4e984332653a806da" class\="tgtSentence"\>WM\_COMPAREITEM\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb775921)|**OCM\_COMPAREITEM**|  
|[\<caps:sentence id\="tgt34" sentenceid\="788353476482225cba177b38a64c12fc" class\="tgtSentence"\>WM\_HSCROLL\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb787575)|**OCM\_HSCROLL**|  
|[\<caps:sentence id\="tgt36" sentenceid\="184504e211dd9d704614b4971227c841" class\="tgtSentence"\>WM\_VSCROLL\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb787577)|**OCM\_VSCROLL**|  
|[\<caps:sentence id\="tgt38" sentenceid\="5472066e1b7be200d04d419a3a7d9b2e" class\="tgtSentence"\>WM\_PARENTNOTIFY\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms632638.aspx)|**OCM\_PARENTNOTIFY**|  
|[\<caps:sentence id\="tgt40" sentenceid\="023ec208a39d8192158a43906a5d18b5" class\="tgtSentence"\>WM\_NOTIFY\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/bb775583)|**OCM\_NOTIFY**|  
  
> [!NOTE]
>  If the control runs on a Win32 system, there are several types of **WM\_CTLCOLOR\*** messages it may receive.  For more information, see **WM\_CTLCOLORBTN**, **WM\_CTLCOLORDLG**, **WM\_CTLCOLOREDIT**, **WM\_CTLCOLORLISTBOX**, **WM\_CTLCOLORMSGBOX**, **WM\_CTLCOLORSCROLLBAR**, **WM\_CTLCOLORSTATIC**.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)   
 [TN062: Windows 컨트롤에 대한 메시지 리플렉션](../mfc/tn062-message-reflection-for-windows-controls.md)