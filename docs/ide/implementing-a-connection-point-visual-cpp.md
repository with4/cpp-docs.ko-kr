---
title: 연결 지점 (Visual c + +) 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b75bf145da401ad9889353a1e65448831c602c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-a-connection-point-visual-c"></a>연결 지점 구현(Visual C++)
연결 지점 구현 마법사를 사용 하 여 연결점을 구현 하려면 해야 프로젝트를 만들었다고는 ATL 지원을 포함 하는 MFC 응용 프로그램 또는 ATL COM 응용 프로그램으로 합니다. 사용할 수는 [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md) ATL 응용 프로그램을 만드는 또는 [MFC 응용 프로그램에 ATL 개체를 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC 응용 프로그램에 대 한 ATL 지원을 구현 하 합니다.  
  
> [!NOTE]
>  MFC 프로젝트에 대 한 연결 지점을 구현 하는 방법에 대 한 정보를 참조 하십시오. [연결점](../mfc/connection-points.md)합니다.  
  
 연결 지점을 구현 하는 프로젝트를 만들 되 면 먼저 ATL 개체를 추가 해야 합니다. 참조 [ATL 프로젝트에 추가 하는 개체 및 컨트롤](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) ATL 프로젝트에 개체를 추가 하는 마법사의 목록에 대 한 합니다.  
  
> [!NOTE]
>  마법사는 ATL 대화 상자, ATL 서버, 성능 개체 또는 성능 카운터를 사용 하 여 만든 XML 웹 서비스를 지원 하지 않습니다.  
  
 연결 가능 개체 (즉, 원본) 각 송신 인터페이스에 대 한 연결점을 노출할 수 있습니다. 클라이언트에서는 개체 (싱크)에 대해 각 송신 인터페이스를 구현할 수 있습니다. 자세한 내용은 참조 [ATL 연결 지점](../atl/atl-connection-points.md)합니다.  
  
### <a name="to-implement-a-connection-point"></a>연결 지점을 구현 하려면  
  
1.  클래스 뷰에서 ATL 개체에 대 한 클래스 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  클릭 **추가** 바로 가기 메뉴를 클릭 한 다음 **연결 지점 추가** 표시 하는 [연결 지점 구현 마법사](../ide/implement-connection-point-wizard.md)합니다.  
  
3.  클릭 하 고 적절 한 형식 라이브러리에서 구현할 연결 지점 인터페이스 선택 **마침**합니다.  
  
4.  클래스 뷰에서 각 연결 지점에 대해 생성 된 프록시 클래스를 검사 합니다. CProxy로 표시 된 클래스*InterfaceName*\<T >에서 파생 되 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)합니다.  
  
5.  연결 지점 클래스의 정의 표시 하려면 연결 지점 클래스를 두 번 클릭 합니다.  
  
    -   사용자 고유의 프로젝트의 인터페이스에 대 한 연결 지점을 구현 하는 경우 다음 정의 표시  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         로컬 인터페이스를 구현 하는 경우 메서드 및 속성 클래스 본문에 나타납니다.  
  
    -   제네릭 인터페이스가 다른 인터페이스에 대 한 연결 지점을 구현 하는 경우 인터페이스의 메서드를 포함 하는 정의 각 앞에 붙습니다 `Fire_`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [개체에 연결 지점 추가](../atl/adding-connection-points-to-an-object.md)