---
title: "ATL 프로젝트에 새 인터페이스 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.interface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 인터페이스 추가"
  - "컨트롤[ATL], 인터페이스"
  - "인터페이스 구현 ATL 마법사"
  - "인터페이스, ATL 개체에 추가"
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL 프로젝트에 새 인터페이스 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 또는 컨트롤에 인터페이스를 추가할 때는 해당 인터페이스의 각 메서드에 대해 스텁 아웃 함수를 만듭니다.  개체 또는 컨트롤에는 현재 기존의 형식 라이브러리에 있는 인터페이스만 추가할 수 있습니다.  또한 인터페이스를 추가할 클래스는 [BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md) 매크로를 구현해야 하며 특성을 사용하는 프로젝트인 경우에는 `coclass` 특성이 있어야 합니다.  
  
 컨트롤에 새 인터페이스를 추가하려면 수동으로 추가하거나 클래스 뷰에서 코드 마법사를 사용하여 추가할 수 있습니다.  
  
### 클래스 뷰에서 코드 마법사를 사용하여 기존 개체 또는 컨트롤에 인터페이스를 추가하려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 컨트롤의 클래스 이름을 마우스 오른쪽 단추로 클릭합니다.  예를 들면, 전체 컨트롤이나 복합 컨트롤 또는 헤더 파일에 BEGIN\_COM\_MAP 매크로를 구현하는 그 밖의 컨트롤 클래스가 있습니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **인터페이스 구현**을 클릭합니다.  
  
3.  [인터페이스 구현 마법사](../../ide/implement-interface-wizard.md)에서 구현할 인터페이스를 선택합니다.  구현할 인터페이스가 사용할 수 있는 형식 라이브러리에 없으면 .idl 파일에 수동으로 추가해야 합니다.  
  
### 수동으로 새 인터페이스를 추가하려면  
  
1.  새 인터페이스의 정의를 .idl 파일에 추가합니다.  
  
2.  인터페이스에서 개체 또는 컨트롤을 파생시킵니다.  
  
3.  인터페이스에 대한 새로운 [COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20\(ATL\).md)를 만들거나, 특성을 사용하는 프로젝트인 경우에는 `coclass` 특성을 추가합니다.  
  
4.  인터페이스에 메서드를 구현합니다.  
  
## 참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+ 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)