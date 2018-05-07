---
title: 함수에 메시지 매핑 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3388cd8e9a52ef9aacb427d66b027d793b08ca75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mapping-messages-to-functions"></a>함수에 메시지 매핑
속성 창 응용 프로그램의 리소스에 의해 생성 된 메시지에 메시지 처리기 (MFC 사용자 인터페이스 클래스의 멤버 함수)에 바인딩할 수 있습니다. 사용할 [MFC 메시지 맵에](../../mfc/messages-and-commands-in-the-framework.md) 의 바인딩을 만들 수 있습니다.  
  
 클래스 뷰를 사용 하 여 프레임 워크 클래스 중 하나에서 파생 된 새 클래스를 만들 때 해당 클래스가 자동으로 배치에 완전 한 기능적 헤더 (.h) 및 구현 (.cpp)에서 지정 하는 파일입니다.  
  
> [!NOTE]
>  메시지를 처리 하지 않는 새 클래스를 추가 하려면 텍스트 편집기에서 직접 클래스를 만듭니다.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>정의 하거나 속성 창을 사용 하 여 메시지 처리기를 제거 하려면  
  
1.  클래스 뷰에서 클래스를 클릭 합니다.  
  
2.  속성 창에서 클릭 된 **메시지** 단추입니다.  
  
    > [!NOTE]
    >  **메시지** 클래스 뷰 또는 소스 창 내부를 클릭할 때의 클래스 이름 중 하나를 선택 하면 단추는 사용할 수 있습니다.  
  
     프로젝트에는 메시지에 대 한 처리기를 처리기의 이름은 메시지 옆의 오른쪽 열에 나타납니다.  
  
3.  메시지 처리기가 없으면, 하는 경우로 처리기의 제안된 된 이름을 표시 하려면 속성 창에서 오른쪽 열에서 셀을 클릭 \<추가 >*HandlerName*합니다. (예를 들어는 `WM_TIMER` 메시지 처리기 제안 \<추가 >`OnTimer`).  
  
4.  제안 된 이름을 함수에 대 한 스텁 코드를 추가 하려면 클릭 합니다.  
  
5.  메시지 처리기를 편집 하려면 클래스 뷰에서 메시지를 두 번 클릭 하 고 소스 창에서 코드를 편집 합니다.  
  
 메시지 처리기를 제거 하려면 오른쪽 열에 대 한 처리기를 두 번 클릭 하 고 선택 \<삭제 >*HandlerName*합니다. 함수 코드 주석으로 처리 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [대화 상자 컨트롤에 대 한 이벤트 처리기를 추가합니다.](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [클래스 구조 탐색](../../ide/navigating-the-class-structure-visual-cpp.md)
