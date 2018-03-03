---
title: "대화 상자 컨트롤에 대 한 멤버 변수 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb966459695eb048943a12e33c8e909f99fdc92b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="defining-member-variables-for-dialog-controls"></a>대화 상자 컨트롤의 멤버 변수 정의
단추를 제외한 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면 다음 메서드를 사용할 수 있습니다.  
  
> [!NOTE]
>  이 항목은 MFC 프로젝트 내의 대화 상자 컨트롤에만 적용됩니다. ATL 프로젝트는 **새 Windows 메시지 및 이벤트 처리기** 대화 상자.  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>(단추 이외의) 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면  
  
1.  에 [대화 상자 편집기](../windows/dialog-editor.md), 컨트롤을 선택 합니다.  
  
2.  누른 채는 **CTRL** 키, 대화 상자 컨트롤을 두 번 클릭 합니다.  
  
     [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 나타납니다.  
  
3.  입력에 적절 한 정보는 **멤버 변수 추가** 마법사. 자세한 내용은 참조 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)합니다.  
  
4.  클릭 **확인** 대화 상자 편집기로 돌아갑니다.  
  
    > [!TIP]
    >  대화 상자 컨트롤에서 기존 처리기로 이동하려면 컨트롤을 두 번 클릭합니다.  
  

  
 사용할 수도 있습니다는 **멤버 변수** 탭에서 **MFC 클래스 마법사** 를 추가 하는 지정 된 클래스에 대 한 새 멤버 변수에 이미 정의 하는 것입니다.  
  
 요구 사항  
  
 MFC  
  
## <a name="see-also"></a>참고 항목  
 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC 클래스 마법사](../mfc/reference/mfc-class-wizard.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)

