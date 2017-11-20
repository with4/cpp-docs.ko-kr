---
title: "인터페이스 (Visual c + +) 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caea9442973d131e99b3f52ca36a6cf991f2410a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-an-interface-visual-c"></a>인터페이스 구현(Visual C++)
인터페이스를 구현 하려면 해야 프로젝트를 만들었다고는 ATL 지원을 포함 하는 MFC 응용 프로그램 또는 ATL COM 응용 프로그램으로 합니다. 사용할 수는 [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md) ATL 응용 프로그램을 만드는 또는 [MFC 응용 프로그램에 ATL 개체를 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC 응용 프로그램에 대 한 ATL 지원을 구현 하 합니다.  
  
 인터페이스를 구현 하기 위해 프로젝트를 만들 되 면 먼저 ATL 개체를 추가 해야 합니다. 참조 [ATL 프로젝트에 추가 하는 개체 및 컨트롤](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) ATL 프로젝트에 개체를 추가 하는 마법사의 목록에 대 한 합니다.  
  
> [!NOTE]
>  마법사는 ATL 대화 상자, ATL, 성능 개체 또는 성능 카운터를 사용 하 여 XML Web services를 지원 하지 않습니다.  
  
 경우 있습니다 [ATL 컨트롤 추가](../atl/reference/adding-an-atl-control.md)에 표시 된 기본 인터페이스를 구현 여부를 지정할 수 있습니다는 [인터페이스](../atl/reference/interfaces-atl-control-wizard.md) 페이지는 마법사 및 atlcom.h에서 정의 합니다.  
  
 개체 또는 컨트롤을 추가 하면 인터페이스 구현 마법사를 사용 하 여 모든 사용 가능한 형식 라이브러리에 있는 다른 인터페이스를 구현할 수 있습니다.  
  
 새 인터페이스를 추가 하는 경우 프로젝트의.idl 파일에 수동으로 추가 해야 있습니다. 참조 [ATL 프로젝트에 새 인터페이스를 추가](../atl/reference/adding-a-new-interface-in-an-atl-project.md) 자세한 정보에 대 한 합니다.  
  
### <a name="to-implement-an-interface"></a>인터페이스를 구현 하려면  
  
1.  클래스 뷰에서 ATL 개체에 대 한 클래스 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  클릭 **추가** 바로 가기 메뉴를 클릭 한 다음 **인터페이스 구현** 표시 하는 [인터페이스 구현 마법사](../ide/implement-interface-wizard.md)합니다.  
  
3.  인터페이스를 적절 한 형식 라이브러리에서 구현 하 고 클릭 하 여 선택한 **마침**합니다.  
  
4.  클래스 뷰에서 확장 개체의 기본 및 인터페이스 노드 다음의 사용 가능한 속성, 메서드 및 이벤트를 볼 수 있는 인터페이스의 노드를 확장을 구현한 인터페이스를 참조 하십시오.  
  
    > [!NOTE]
    >  사용할 수도 있습니다는 [개체 브라우저](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) 인터페이스의 멤버를 검사할 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 인터페이스 만들기](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM 인터페이스 편집](../ide/editing-a-com-interface.md)