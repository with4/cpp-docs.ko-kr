---
title: "인터페이스 구현(Visual C++) | Microsoft Docs"
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
  - "인터페이스, 구현"
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 인터페이스 구현(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스를 구현하려면 프로젝트를 ATL COM 응용 프로그램이나 ATL을 지원하는 MFC 응용 프로그램으로 만들어야 합니다.  [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나 [MFC 응용 프로그램에 ATL 개체를 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램에 ATL 지원을 구현할 수 있습니다.  
  
 프로젝트를 만든 후 인터페이스를 구현하려면 먼저 ATL 개체를 추가해야 합니다.  ATL 프로젝트에 개체를 추가하는 마법사 목록은 [ATL 프로젝트에 개체 및 컨트롤 추가](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)를 참조하십시오.  
  
> [!NOTE]
>  마법사에서는 ATL 대화 상자, ATL을 사용하는 XML Web services, 성능 개체 또는 성능 카운터를 지원하지 않습니다.  
  
 [ATL 컨트롤을 추가](../atl/reference/adding-an-atl-control.md)할 경우 마법사의 [인터페이스](../atl/reference/interfaces-atl-control-wizard.md) 페이지에 표시되어 있으며 atlcom.h에 정의되어 있는 기본 인터페이스를 구현할지 여부를 지정할 수 있습니다.  
  
 개체나 컨트롤을 추가한 후 인터페이스 구현 마법사를 사용하여 사용 가능한 모든 형식 라이브러리에 있는 다른 인터페이스를 구현할 수 있습니다.  
  
 인터페이스를 새로 추가할 경우에는 프로젝트의 .idl 파일에 해당 인터페이스를 직접 추가해야 합니다.  자세한 내용은 [ATL 프로젝트에 새 인터페이스 추가](../atl/reference/adding-a-new-interface-in-an-atl-project.md)를 참조하십시오.  
  
### 인터페이스를 구현하려면  
  
1.  클래스 뷰에서 ATL 개체의 클래스 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **인터페이스 구현**을 클릭하여 [인터페이스 구현 마법사](../ide/implement-interface-wizard.md)를 표시합니다.  
  
3.  해당하는 형식 라이브러리에서 구현할 인터페이스를 선택한 다음 **마침**을 클릭합니다.  
  
4.  클래스 뷰에서 개체의 기본 및 인터페이스 노드를 확장하여 구현된 인터페이스를 살펴 본 다음 인터페이스의 노드를 확장하여 사용 가능한 속성, 메서드 및 이벤트를 봅니다.  
  
    > [!NOTE]
    >  [개체 브라우저](http://msdn.microsoft.com/ko-kr/f89acfc5-1152-413d-9f56-3dc16e3f0470)를 사용하여 인터페이스의 멤버를 검토할 수도 있습니다.  
  
## 참고 항목  
 [COM 인터페이스 만들기](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM 인터페이스 편집](../ide/editing-a-com-interface.md)