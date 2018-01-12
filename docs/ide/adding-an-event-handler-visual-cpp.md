---
title: "이벤트 처리기 (Visual c + +)를 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.eventhandler.overview
dev_langs: C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9a5380bf335a13bbf7b2f54840c9d1160187167
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-event-handler-visual-c"></a>이벤트 처리기 추가(Visual C++)
리소스 편집기에서 새 이벤트 처리기를 추가 하거나 기존 이벤트 처리기를 사용 하 여 대화 상자 컨트롤을 편집할 수는 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)합니다.  
  
 이벤트를 사용 하 여 대화 상자를 구현 하는 클래스를 추가할 수는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 대화 상자 클래스 이외의 다른 클래스에 이벤트를 추가 하려면 이벤트 처리기 마법사를 사용 합니다.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>대화 상자 컨트롤에 이벤트 처리기를 추가 하려면  
  
1.  대화 상자 리소스를 두 번 클릭 [리소스 뷰](../windows/resource-view-window.md) 에서 컨트롤이 포함 된 대화 상자 리소스를 열려면는 [대화 상자 편집기](../windows/dialog-editor.md)합니다.  
  
2.  알림 이벤트를 처리 하려는 컨트롤을 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴를 클릭 **이벤트 처리기 추가** 이벤트 처리기 마법사를 표시 합니다.  
  
4.  이벤트를 선택 하는 **메시지 유형을** 상자에서 선택한 클래스에 추가할 수는 **클래스 목록** 상자입니다.  
  
5.  기본 이름을 그대로 **함수 처리기 이름** 하거나 원하는 이름을 제공 합니다.  
  
6.  클릭 **추가 및 편집** 프로젝트에 이벤트 처리기를 추가 하 고 적절 한 이벤트 처리기 코드를 추가 하려면 새 함수에서 텍스트 편집기를 엽니다.  
  
     선택한 메시지 유형 선택된 된 클래스에 대 한 이벤트 처리기가 이미 있으면 **추가 및 편집** 를 사용할 수 없으면 및 **코드 편집** ´ ï ´ 합니다. 클릭 **코드 편집** 기존 함수에서 텍스트 편집기를 엽니다.  
  
 또는 이벤트 처리기를 추가할 수 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 참조 [대화 상자 컨트롤에 대 한 이벤트 처리기 추가](../windows/adding-event-handlers-for-dialog-box-controls.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)