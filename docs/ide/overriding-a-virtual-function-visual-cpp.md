---
title: "재정의 가상 함수 (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98e77579d511f4c78f0f7835c0b3c1dcea632734
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-a-virtual-function-visual-c"></a>가상 함수 재정의(Visual C++)
Visual Studio에서 기본 클래스에 정의 된 가상 함수를 재정의할 수 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>속성 창에서 가상 함수 재정의 하려면  
  
1.  클래스 뷰에서 클래스를 클릭 합니다.  
  
2.  속성 창에서 클릭 된 **재정의** 단추입니다.  
  
    > [!NOTE]
    >  **재정의** 클래스 뷰 또는 소스 창 내부를 클릭할 때의 클래스 이름 중 하나를 선택 하면 단추는 사용할 수 있습니다.  
  
     왼쪽된 열에서 가상 함수를 나열 합니다. 가상 함수 이름을 오른쪽 열에 나타나면 다음 재정의 이미 구현 되었습니다.  
  
3.  함수는 함수의 제안 이름을 속성 창에서 오른쪽 열에 셀을 클릭 재정의 하지 않은 경우에 우선 \<추가 >*FuncName*합니다.  
  
4.  제안 된 이름을 함수에 대 한 스텁 코드를 추가 하려면 클릭 합니다.  
  
5.  재정의 함수를 편집 하려면 클래스 뷰에서 함수 이름을 두 번 클릭 하 고 소스 창에서 코드를 편집 합니다.  
  
 재정의 제거 하려면 오른쪽 열에 재정의 함수 이름을 클릭 하 고 선택 \<삭제 >*FuncName*합니다. 함수 코드 주석으로 처리 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)