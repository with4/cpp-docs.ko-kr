---
title: 가상 함수 재정의(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337745"
---
# <a name="overriding-a-virtual-function-visual-c"></a>가상 함수 재정의(Visual C++)
Visual Studio [속성 창](/visualstudio/ide/reference/properties-window)에서 기본 클래스에 정의된 가상 함수를 재정의할 수 있습니다.  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>속성 창에서 가상 함수를 재정의하려면  
  
1.  클래스 뷰에서 클래스를 클릭합니다.  
  
2.  속성 창에서 **재정의** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  클래스 뷰에서 클래스 이름을 선택하거나 소스 창 내에서 클릭하면 **재정의** 단추를 사용할 수 있습니다.  
  
     왼쪽 열은 가상 함수를 나열합니다. 가상 함수의 이름이 오른쪽 열에도 나타나면 재정의가 이미 구현된 것입니다.  
  
3.  함수에 재정의가 없는 경우, 속성 창에서 오른쪽 열에 있는 셀을 클릭하여 \<add*FuncName*과 같은 함수 재정의의 제안된 이름이 표시됩니다.  
  
4.  제안된 이름을 클릭하여 함수의 스텁 코드를 추가합니다.  
  
5.  재정의 함수를 편집하려면 클래스 뷰에서 함수 이름을 두 번 클릭하고 소스 창에서 코드를 편집합니다.  
  
 재정의를 제거하려면 오른쪽 열의 재정의 함수 이름을 클릭하고 \<delete>*FuncName*을 선택합니다. 함수의 코드는 주석으로 처리됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)