---
title: 대화 상자 컨트롤에 대 한 멤버 변수 정의 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1f5cee3bf827effc7c99dd66d7dc2898c9ad55f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645466"
---
# <a name="defining-member-variables-for-dialog-controls"></a>대화 상자 컨트롤의 멤버 변수 정의
단추를 제외한 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면 다음 메서드를 사용할 수 있습니다.  
  
> [!NOTE]
>  이 항목은 MFC 프로젝트 내의 대화 상자 컨트롤에만 적용됩니다. ATL 프로젝트를 사용 해야 합니다 **새 Windows 메시지 및 이벤트 처리기** 대화 상자.  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>(단추 이외의) 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면  
  
1.  에 [대화 상자 편집기](../windows/dialog-editor.md), 컨트롤을 선택 합니다.  
  
2.  누른 채 합니다 **Ctrl** 키, 대화 상자 컨트롤을 두 번 클릭 합니다.  
  
     합니다 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 나타납니다.  
  
3.  적절 한 정보를 입력 합니다 **멤버 변수 추가** 마법사. 자세한 내용은 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)합니다.  
  
4.  클릭 **확인** 돌아가려면 합니다 **대화 상자** 편집기입니다.  
  
    > [!TIP]
    >  대화 상자 컨트롤에서 기존 처리기로 이동하려면 컨트롤을 두 번 클릭합니다.  
  
 사용할 수도 있습니다는 **멤버 변수** 탭에서 **MFC 클래스 마법사** , 지정된 된 클래스에 대 한 새 멤버 변수를 추가 하 여 이미 정의 된 해당 합니다.  
  
## <a name="requirements"></a>요구 사항  
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