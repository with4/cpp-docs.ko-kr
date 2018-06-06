---
title: 이벤트 처리기 추가(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184161b22358f77845b5f7c4b6da0bb42f3ea15f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33324917"
---
# <a name="adding-an-event-handler-visual-c"></a>이벤트 처리기 추가(Visual C++)
리소스 편집기에서 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)를 사용하여 대화 상자 컨트롤에 대해 새 이벤트 처리기를 추가하거나 기존 이벤트 처리기를 편집할 수 있습니다.  
  
 [속성 창](/visualstudio/ide/reference/properties-window)을 사용하여 대화 상자를 구현하는 클래스에 이벤트를 추가할 수 있습니다. 대화 상자 클래스 이외의 다른 클래스에 이벤트를 추가하려면 이벤트 처리기 마법사를 사용합니다.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>대화 상자 컨트롤에 이벤트 처리기를 추가하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)에서 대화 상자 리소스를 두 번 클릭하여 [대화 상자 편집기](../windows/dialog-editor.md)의 컨트롤이 포함된 대화 상자 리소스를 엽니다.  
  
2.  알림 이벤트를 처리할 컨트롤을 마우스 오른쪽 단추로 클릭합니다.  
  
3.  바로 가기 메뉴에서 **이벤트 처리기 추가**를 클릭하여 이벤트 처리기 마법사를 표시합니다.  
  
4.  **메시지 유형** 상자에서 이벤트를 선택하여 **클래스 목록** 상자에서 선택한 클래스를 추가합니다.  
  
5.  **함수 처리기 이름** 상자에서 기본 이름을 수락하거나 원하는 이름을 제공합니다.  
  
6.  **추가 및 편집**을 클릭하여 이벤트 처리기를 프로젝트에 추가하고, 새 함수에서 텍스트 편집기를 열어 적절한 이벤트 처리기 코드를 추가합니다.  
  
     선택한 메시지 유형에 선택한 클래스에 대한 이벤트 처리기가 이미 있는 경우, **추가 및 편집**을 사용할 수 없고 **코드 편집**을 사용할 수 있습니다. **코드 편집**을 클릭하여 기존 함수에서 텍스트 편집기를 엽니다.  
  
 또는 [속성 창](/visualstudio/ide/reference/properties-window)에서 이벤트 처리기를 추가할 수 있습니다. 자세한 내용은 [대화 상자 컨트롤에 대한 이벤트 처리기 추가](../windows/adding-event-handlers-for-dialog-box-controls.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)