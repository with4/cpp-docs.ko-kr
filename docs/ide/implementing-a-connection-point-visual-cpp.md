---
title: "연결 지점 구현(Visual C++) | Microsoft Docs"
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
  - "연결 지점[C++], 구현"
  - "연결 지점 구현 마법사[C++]"
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연결 지점 구현(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

연결 지점 구현 마법사를 사용하여 연결 지점을 구현하려면 프로젝트를 ATL COM 응용 프로그램이나 ATL을 지원하는 MFC 응용 프로그램으로 만들어야 합니다.  [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나 [MFC 응용 프로그램에 ATL 개체를 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램에 ATL 지원을 구현할 수 있습니다.  
  
> [!NOTE]
>  MFC 프로젝트의 연결 지점 구현에 대한 자세한 내용은 [연결 지점](../mfc/connection-points.md)을 참조하십시오.  
  
 프로젝트를 만든 후 연결 지점을 구현하려면 먼저 ATL 개체를 추가해야 합니다.  ATL 프로젝트에 개체를 추가하는 마법사 목록은 [ATL 프로젝트에 개체 및 컨트롤 추가](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)를 참조하십시오.  
  
> [!NOTE]
>  마법사에서는 ATL 대화 상자, ATL 서버를 사용하여 만들어지는 XML Web services, 성능 개체 또는 성능 카운터를 지원하지 않습니다.  
  
 연결 가능 개체\(즉, 소스\)에서는 해당하는 보내기 인터페이스 각각에 대해 연결 지점을 노출할 수 있습니다.  클라이언트에서는 개체\(즉, 싱크\)에 대해 각 보내기 인터페이스를 구현할 수 있습니다.  자세한 내용은 [ATL 연결 지점](../atl/atl-connection-points.md)을 참조하십시오.  
  
### 연결 지점을 구현하려면  
  
1.  클래스 뷰에서 ATL 개체의 클래스 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **연결 지점 추가**를 클릭하여 [연결 지점 구현 마법사](../ide/implement-connection-point-wizard.md)를 표시합니다.  
  
3.  해당하는 형식 라이브러리에서 구현할 연결 지점 인터페이스를 선택한 다음 **마침**을 클릭합니다.  
  
4.  클래스 뷰에서 각 연결 지점에 대해 만든 프록시 클래스를 검토합니다.  해당 클래스는 CProxy*InterfaceName*\<T\>으로 표시되며 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)에서 파생됩니다.  
  
5.  연결 지점 클래스를 두 번 클릭하여 연결 지점 클래스의 정의를 표시합니다.  
  
    -   자신의 프로젝트 인터페이스에 대한 연결 지점을 구현할 경우 다음과 같은 정의가 나타납니다.  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         로컬 인터페이스를 구현할 경우 클래스 본문에 메서드와 속성이 나타납니다.  
  
    -   다른 인터페이스에 대한 연결 지점을 구현할 경우 앞에 `Fire_`가 붙은 인터페이스의 메서드가 정의에 포함됩니다.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding Connection Points to an Object](../atl/adding-connection-points-to-an-object.md)