---
title: "속성 추가(Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인터페이스, 속성 추가"
  - "속성[C++], 인터페이스에 추가"
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 속성 추가(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[속성 추가 마법사](../ide/names-add-property-wizard.md)를 사용하면 프로젝트의 인터페이스에 메서드를 추가할 수 있습니다.  
  
### 속성을 개체에 추가하려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 속성을 추가할 인터페이스 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
    > [!NOTE]
    >  프로젝트에서 특성을 사용하지 않으면 라이브러리 노드 내에 중첩된 dispinterface에도 속성을 추가할 수 있습니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **속성 추가**를 클릭합니다.  
  
3.  [속성 추가 마법사](../ide/names-add-property-wizard.md)에서 속성을 만드는 데 필요한 정보를 지정합니다.  
  
4.  이 마법사의 [IDL 특성](../ide/idl-attributes-add-property-wizard.md) 페이지에서 속성에 IDL\(인터페이스 정의 언어\) 설정을 지정합니다.  
  
5.  **마침**을 클릭하여 속성을 추가합니다.  
  
 속성의 **Get** 및 `Put` 메서드가 클래스 뷰에서 속성이 정의된 인터페이스 밑에 두 개의 아이콘으로 표시됩니다.  두 아이콘 중 하나를 두 번 클릭하면 .idl 파일의 속성 선언을 볼 수 있습니다.  
  
-   ATL 인터페이스의 경우, **Get**과 **Put** 함수는 .cpp 파일에 추가되고 이 함수에 대한 참조는 .h 파일에 추가됩니다.  
  
-   MFC dispinterface의 경우, **멤버 변수**를 구현 형식으로 선택하면 이를 구현하는 클래스에 메서드와 변수가 추가됩니다.  **Get\/Set 메서드**를 구현 형식으로 선택하면 이를 구현하는 클래스에 두 개의 메서드가 추가됩니다.  
  
## 참고 항목  
 [COM 인터페이스 만들기](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM 인터페이스 편집](../ide/editing-a-com-interface.md)   
 [구성 요소 개체 모델](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [인터페이스 포인터 및 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms688484)