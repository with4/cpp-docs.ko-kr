---
title: 창 메시지 Id를 반영 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OCM_CTLCOLORBTN
- OCM_PARENTNOTIFY
- OCM_VKEYTOITEM
- OCM_CTLCOLORSTATIC
- OCM_HSCROLL
- OCM_CHARTOITEM
- OCM_DRAWITEM
- OCM_MEASUREITEM
- OCM_COMPAREITEM
- OCM_COMMAND
- OCM_NOTIFY
- OCM_CTLCOLORMSGBOX
- OCM_DELETEITEM
- OCM_CTLCOLORLISTBOX
- OCM_CTLCOLORDLG
- OCM_CTLCOLOREDIT
- OCM_CTLCOLORSCROLLBAR
- OCM_VSCROLL
- OCM_CTLCOLOR
dev_langs:
- C++
helpviewer_keywords:
- OCM_HSCROLL message [MFC]
- OCM_PARENTNOTIFY message [MFC]
- messages, reflected
- reflected messages, window message Ids
- OCM_CTLCOLORDLG message [MFC]
- OCM_COMMAND message [MFC]
- OCM_CTLCOLORMSGBOX message [MFC]
- OCM_COMPAREITEM message [MFC]
- OCM_DRAWITEM message [MFC]
- OCM_VSCROLL message [MFC]
- OCM_CTLCOLOREDIT message [MFC]
- OCM_VKEYTOITEM message [MFC]
- OCM_CHARTOITEM message [MFC]
- OCM_CTLCOLORBTN message [MFC]
- OCM_CTLCOLORSTATIC message [MFC]
- OCM_MEASUREITEM message [MFC]
- OCM_CTLCOLOR message [MFC]
- OCM_CTLCOLORSCROLLBAR message [MFC]
- OCM_ messages
- OCM_DELETEITEM message [MFC]
- OCM_CTLCOLORLISTBOX message [MFC]
- OCM_NOTIFY message [MFC]
- reflected messages
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8746666c4b1eb48e4c54822f76328579b7ce8584
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928200"
---
# <a name="reflected-window-message-ids"></a>리플렉션된 창 메시지 ID
ActiveX 컨트롤 또는 기타 특수 컨트롤을 만드는 빠른 방법을 창에 하위 클래스입니다. 자세한 내용은 참조 [MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)합니다.  
  
 컨트롤의 컨테이너는 서브클래싱된 Windows 컨트롤을 전송한 창 메시지를 받지 않도록 하려면 [COleControl](../mfc/reference/colecontrol-class.md) 특정 창 메시지를 가로채 고 컨트롤으로 다시 보내야 하는 "구문은 reflector" 창을 만듭니다. 컨트롤의 창 프로시저의 ActiveX 컨트롤에 대 한 적절 한 작업을 수행 하 여 리플 렉 트 된 메시지를 처리할 수 있습니다.  
  
 다음 표에서 차단 된 메시지와 해당 보내는 메시지에 리플렉터 창을 보여 줍니다.  
  
|컨트롤에서 보낸 메시지|컨트롤에 반영 되는 메시지|  
|---------------------------------|--------------------------------------|  
|[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)|OCM_COMMAND|  
|[WM_CTLCOLORBTN](http://msdn.microsoft.com/library/windows/desktop/bb761849)|OCM_CTLCOLORBTN|  
|[WM_CTLCOLOREDIT](http://msdn.microsoft.com/library/windows/desktop/bb761691)|OCM_CTLCOLOREDIT|  
|[WM_CTLCOLORDLG](http://msdn.microsoft.com/library/windows/desktop/ms645417)|OCM_CTLCOLORDLG|  
|[WM_CTLCOLORLISTBOX](http://msdn.microsoft.com/library/windows/desktop/bb761360)|OCM_CTLCOLORLISTBOX|  
|[WM_CTLCOLORSCROLLBAR](http://msdn.microsoft.com/library/windows/desktop/bb787573)|OCM_CTLCOLORSCROLLBAR|  
|[WM_CTLCOLORSTATIC](http://msdn.microsoft.com/library/windows/desktop/bb787524)|OCM_CTLCOLORSTATIC|  
|[WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923)|OCM_DRAWITEM|  
|[WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925)|OCM_MEASUREITEM|  
|[WM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb761362)|OCM_DELETEITEM|  
|[WM_VKEYTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761364)|OCM_VKEYTOITEM|  
|[WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358)|OCM_CHARTOITEM|  
|[WM_COMPAREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775921)|OCM_COMPAREITEM|  
|[WM_HSCROLL](http://msdn.microsoft.com/library/windows/desktop/bb787575)|OCM_HSCROLL|  
|[WM_VSCROLL](http://msdn.microsoft.com/library/windows/desktop/bb787577)|OCM_VSCROLL|  
|[창에 WM_PARENTNOTIFY](https://msdn.microsoft.com/library/ms632638.aspx)|OCM_PARENTNOTIFY|  
|[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)|OCM_NOTIFY|  
  
> [!NOTE]
>  WM_CTLCOLOR의 유형은 여러 가지가 컨트롤에서는 Win32 시스템에서 실행 하는 경우\* 메시지를 받을 수 있습니다. 자세한 내용은 WM_CTLCOLORBTN, WM_CTLCOLORDLG, WM_CTLCOLOREDIT, WM_CTLCOLORLISTBOX, WM_CTLCOLORMSGBOX, WM_CTLCOLORSCROLLBAR, WM_CTLCOLORSTATIC를 참조 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)   
 [TN062: Windows 컨트롤에 대한 메시지 리플렉션](../mfc/tn062-message-reflection-for-windows-controls.md)

