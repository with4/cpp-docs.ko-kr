---
title: "리플 렉 트 된 메시지에 대 한 메시지 처리기 정의 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages, reflected
- message handling, reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0033c75d351aa201a0c18e81395d764b9d45761b
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>리플렉트된 메시지의 메시지 처리기 정의
새 MFC 컨트롤 클래스를 만든 후에 대 한 메시지 처리기를 정의할 수 있습니다. 리플 렉 트 된 메시지 처리기는 부모에 의해 메시지를 수신 하기 전에 자체 메시지를 처리 하 여 컨트롤 클래스를 허용 합니다. MFC를 사용할 수 있습니다 [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) 제어에서 부모 창에 메시지를 보내는 함수입니다.  
  
 예를 들어 해도이 기능을 사용 하 여 자체는 다시 그리게 하는 목록 상자를 만들 의존 하기 보다는 (소유자 그리기)를 위해 부모 창에 있습니다. 리플 렉 트 된 메시지에 대 한 자세한 내용은 참조 하십시오. [리플렉션된 메시지 처리](../../mfc/handling-reflected-messages.md)합니다.  
  
 만들려는 [ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md) 같은 기능을 갖춘 ActiveX 컨트롤에 대 한 프로젝트를 만들어야 합니다.  
  
> [!NOTE]
>  리플 렉 트 된 메시지를 추가할 수 없습니다 (OCM_*메시지*) ActiveX 제어 속성 창을 사용 하 여 아래에서 설명 합니다. 이러한 메시지는 수동으로 추가 해야 합니다.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>속성 창에서 리플 렉 트 된 메시지에 대 한 메시지 처리기를 정의 하려면  
  
1.  예: 목록 컨트롤, rebar 컨트롤, 도구 모음 또는 트리 컨트롤을 MFC 프로젝트에 추가 합니다.  
  
2.  클래스 뷰의 컨트롤 클래스의 이름을 클릭 합니다.  
  
3.  에 [속성 창](/visualstudio/ide/reference/properties-window)에 컨트롤 클래스 이름이 표시는 **클래스 이름** 목록입니다.  
  
4.  클릭 된 **메시지** 단추 컨트롤에 추가할 수 있는 Windows 메시지를 표시 합니다.  
  
5.  머리글 표시 될 때까지 속성 창에 있는 메시지의 목록 아래로 스크롤하여 **리플렉션**합니다. 또는 클릭 하 고는 **범주** 단추는 뷰 참조를 축소 하는 **리플렉션** 제목입니다.  
  
6.  리플 렉 트 된 메시지 처리기를 정의 하려면 선택 합니다. 리플 렉 트 된 메시지는 등호 (=)로 표시 됩니다.  
  
7.  처리기로의 제안된 된 이름을 표시 하려면 속성 창의 오른쪽 열에서 셀을 클릭 \<추가 >*HandlerName*합니다. (예를 들어는 **WM_CTLCOLOR =** 메시지 처리기 제안 \<추가 >**CtlColor**).  
  
8.  제안된 된 이름을 수락을 클릭 합니다. 처리기는 프로젝트에 추가 됩니다.  
  
     리플 렉 트 된 메시지 창의 오른쪽 열에 추가 된 메시지 처리기 이름이 나타납니다.  
  
9. 를 편집 하거나 메시지 처리기를 삭제 하려면 4-7 단계를 반복 합니다. 편집 또는 삭제 및 적절 한 작업을 클릭 하 고 처리기 이름을 포함 하는 셀을 클릭 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)

