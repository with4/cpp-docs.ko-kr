---
title: "가상 함수 재정의(Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.virtualfunc.override"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기본 클래스, 정의된 가상 함수 재정의"
  - "속성 창, 가상 함수 재정의"
  - "가상 함수, 재정의"
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 가상 함수 재정의(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio [속성 창](../Topic/Properties%20Window.md)에서 기본 클래스에 정의된 가상 함수를 재정의할 수 있습니다.  
  
### 속성 창에서 가상 함수를 재정의하려면  
  
1.  클래스 뷰에서 클래스를 클릭합니다.  
  
2.  속성 창에서 **재정의** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  클래스 뷰에서 클래스 이름을 선택하거나 소스 창 안에서 클래스 이름을 클릭하면 **재정의** 단추를 사용할 수 있습니다.  
  
     왼쪽 열에는 가상 함수가 표시됩니다.  가상 함수 이름이 오른쪽 열에도 나타나면 재정의가 이미 구현된 것입니다.  
  
3.  함수를 재정의하지 않은 경우 속성 창의 오른쪽 열에 있는 셀을 클릭하여 함수 재정의에 대해 제안되는 이름을 \<추가\>*FuncName*으로 표시합니다.  
  
4.  제안된 이름을 클릭하여 함수의 스텁 코드를 추가합니다.  
  
5.  재정의 함수를 편집하려면 클래스 뷰에서 함수 이름을 두 번 클릭한 다음 소스 창에서 코드를 편집합니다.  
  
 재정의를 제거하려면 오른쪽 열에서 재정의 함수 이름을 클릭한 다음 \<삭제\>*FuncName*을 선택합니다.  함수 코드는 주석 처리됩니다.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [클래스 추가](../ide/adding-a-class-visual-cpp.md)   
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)