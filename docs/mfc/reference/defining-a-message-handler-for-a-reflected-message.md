---
title: 리플 렉 트 된 메시지에 대 한 메시지 처리기를 정의 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed941816824c77f14a3364b06af0b3da171ee8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>리플렉트된 메시지의 메시지 처리기 정의
새 MFC 컨트롤 클래스를 만든 후에 대 한 메시지 처리기를 정의할 수 있습니다. 리플 렉 트 된 메시지 처리기는 부모는 메시지를 받기 전에 자체 메시지를 처리 하도록 컨트롤 클래스를 허용 합니다. MFC를 사용할 수 있습니다 [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) 함수를 부모 창에 사용자 컨트롤에서 메시지를 전송 합니다.  
  
 예를 들어 수는이 기능을 사용 하 여 자체는 다시 그리게 하는 목록 상자를 만들 부모 창 (소유자 그린)에 의존 하지 않고 있습니다. 리플 렉 트 된 메시지에 대 한 자세한 내용은 참조 하십시오. [리플렉션된 메시지 처리](../../mfc/handling-reflected-messages.md)합니다.  
  
 만들려는 [ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md) ActiveX 컨트롤에 대 한 프로젝트와 동일한 기능을 만들어야 합니다.  
  
> [!NOTE]
>  리플 렉 트 된 메시지를 추가할 수 없습니다 (OCM_*메시지*) ActiveX 제어 속성 창을 사용 하 여 아래에서 설명 합니다. 이러한 메시지를 수동으로 추가 해야 합니다.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>속성 창에서 리플 렉 트 된 메시지에 대 한 메시지 처리기를 정의 하려면  
  
1.  예: 목록 컨트롤, rebar 컨트롤, 도구 모음 또는 트리 컨트롤을 MFC 프로젝트에 추가 합니다.  
  
2.  클래스 뷰에서 컨트롤 클래스의 이름을 클릭 합니다.  
  
3.  에 [속성 창](/visualstudio/ide/reference/properties-window), 컨트롤 클래스 이름에 표시는 **클래스 이름** 목록입니다.  
  
4.  클릭는 **메시지** 단추 컨트롤에 추가할 수 있는 Windows 메시지를 표시 합니다.  
  
5.  메시지 머리글에 표시 될 때까지 속성 창에서 목록 아래쪽으로 스크롤하여 **리플렉션**합니다. 또는 클릭 하 고는 **범주** 뷰 참조를 축소 하 고 단추는 **리플렉션** 제목입니다.  
  
6.  리플 렉 트 된 메시지 처리기를 정의 하려면 선택 합니다. 리플 렉 트 된 메시지는 등호 (=)로 표시 됩니다.  
  
7.  로 처리기의 제안된 된 이름을 표시 하려면 속성 창에서 오른쪽 열에서 셀을 클릭 \<추가 >*HandlerName*합니다. (예를 들어는 **WM_CTLCOLOR =** 메시지 처리기 제안 \<추가 >**CtlColor**).  
  
8.  제안된 된 이름을 수락을 클릭 합니다. 처리기는 프로젝트에 추가 됩니다.  
  
     리플 렉 트 된 메시지 창의 오른쪽 열에 추가 된 메시지 처리기 이름은 나타납니다.  
  
9. 를 편집 하거나 메시지 처리기를 삭제 하려면 4-7 단계를 반복 합니다. 편집 또는 삭제 하 고 적절 한 작업을 클릭 처리기 이름이 포함 된 셀을 클릭 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)
