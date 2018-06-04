---
title: 인터페이스 구현(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 309ae9dc576f93574836ab4916e87c5232b37a6c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332769"
---
# <a name="implementing-an-interface-visual-c"></a>인터페이스 구현(Visual C++)
인터페이스를 구현하려면 ATL COM 응용 프로그램 또는 ATL 지원이 포함된 MFC 응용 프로그램으로 프로젝트를 만들어야 합니다. [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나 [MFC 응용 프로그램에 ATL 개체를 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램용 ATL 지원을 구현할 수 있습니다.  
  
 프로젝트를 생성한 후 인터페이스를 구현하려면 먼저 ATL 개체를 추가해야 합니다. ATL 프로젝트에 개체를 추가하는 마법사 목록은 [ATL 프로젝트에 개체 및 컨트롤 추가](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)를 참조하세요.  
  
> [!NOTE]
>  이 마법사는 ATL 대화 상자, ATL을 사용하는 XML Web services, 성능 개체 또는 성능 카운터를 지원하지 않습니다.  
  
 [ATL 컨트롤을 추가](../atl/reference/adding-an-atl-control.md)하는 경우, 해당 마법사의 [인터페이스](../atl/reference/interfaces-atl-control-wizard.md) 페이지에 나열되고 atlcom.h에 정의된 기본 인터페이스를 구현할지 여부를 지정할 수 있습니다.  
  
 개체 또는 컨트롤을 추가하면 인터페이스 구현 마법사를 사용하여 모든 사용 가능한 형식 라이브러리에 있는 다른 인터페이스를 구현할 수 있습니다.  
  
 새 인터페이스를 추가하는 경우 프로젝트의 .idl 파일에 수동으로 추가해야 합니다. 자세한 내용은 [ATL 프로젝트에 새 인터페이스 추가](../atl/reference/adding-a-new-interface-in-an-atl-project.md)를 참조하세요.  
  
### <a name="to-implement-an-interface"></a>인터페이스를 구현하려면  
  
1.  클래스 뷰에서 ATL 개체의 클래스 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음, **인터페이스 구현**을 클릭하여 [인터페이스 구현 마법사](../ide/implement-interface-wizard.md)를 표시합니다.  
  
3.  적절한 형식 라이브러리에서 구현할 인터페이스를 선택하고 **마침**을 클릭합니다.  
  
4.  클래스 뷰에서 개체의 기본 및 인터페이스 노드를 확장하여 구현한 인터페이스를 확인한 다음, 인터페이스의 노드를 확장하여 사용 가능한 속성, 메서드 및 이벤트를 확인합니다.  
  
    > [!NOTE]
    >  [개체 브라우저](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470)를 사용하여 인터페이스의 멤버를 검사할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 인터페이스 만들기](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM 인터페이스 편집](../ide/editing-a-com-interface.md)