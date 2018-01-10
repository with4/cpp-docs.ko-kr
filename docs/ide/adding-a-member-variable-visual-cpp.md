---
title: "추가 멤버 변수 (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.classes.member.variable
dev_langs: C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52d98e3eae6e468db7c2737efac8c2b7ab04abd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-member-variable--visual-c"></a>멤버 변수 추가(Visual C++)
클래스 뷰를 사용 하는 클래스에 멤버 변수를 추가할 수 있습니다. 멤버 변수 수에 대 한 [데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md), 또는 제네릭이 될 수 있습니다. 데이터 멤버 변수 마법사와 관련 된 정보가 하 고 요소를 삽입 하는 적절 한 위치에서 소스 파일에서 사용 하도록 설계 된. 멤버 변수를 추가할 수는 [대화 상자 편집기](../windows/dialog-editor.md) 에 [리소스 뷰](../windows/resource-view-window.md), 또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)합니다.  
  
> [!NOTE]
>  디자인 하 고 대화 상자를 구현 있습니다는 것이 더 효율적 대화 상자를 사용 하 여 편집기 대화 상자 컨트롤을 추가 하는 경우 다음 컨트롤의 멤버 변수를 구현 하 고 있습니다.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>리소스 보기 멤버 변수 추가 마법사를 사용 하 여 대화 상자 컨트롤에 대 한 멤버 변수를 추가 하려면  
  
1.  리소스 뷰에서 프로젝트 노드 및 대화 상자는 프로젝트의 목록을 표시 하려면 대화 상자 노드를 확장 합니다.  
  
2.  대화 상자 편집기에서 열려는 멤버 변수를 추가 하려면 대화 상자를 두 번 클릭 합니다.  
  
3.  대화 상자 편집기에 표시 되는 대화 상자에서 멤버 변수를 추가 하려면 컨트롤을 마우스 오른쪽 단추로 클릭 합니다.  
  
4.  바로 가기 메뉴를 클릭 **변수 추가** 표시 하는 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md)합니다.  
  
    > [!NOTE]
    >  기본 값에 제공 되 **컨트롤 ID**합니다.  
  
5.  적절 한 마법사 상자에 정보를 제공 합니다. 참조 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md) 자세한 정보에 대 한 합니다.  
  
6.  클릭 **마침** 를 프로젝트에 정 및 구현 코드를 추가 하 고 마법사를 닫습니다.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>클래스 뷰 멤버 변수 추가 마법사를 사용 하 여 멤버 변수를 추가 하려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)를 프로젝트에 클래스를 표시 하려면 프로젝트 노드를 확장 합니다.  
  
2.  변수를 추가 하려는 클래스를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **변수 추가** 멤버 변수 추가 마법사를 표시 합니다.  
  
4.  적절 한 마법사 상자에 정보를 제공 합니다. 참조 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 대 한 자세한 내용은 합니다.  
  
5.  클릭 **마침** 를 프로젝트에 정 및 구현 코드를 추가 하 고 마법사를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)