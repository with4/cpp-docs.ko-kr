---
title: "ATL 프로젝트에 새 인터페이스를 추가 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8e4916c60310dd8dcbf0bb9e8c1f151309a32621
ms.lasthandoff: 02/24/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL 프로젝트에 새 인터페이스를 추가합니다.
개체 또는 컨트롤에는 인터페이스를 추가 하면 해당 인터페이스의 각 메서드에 대 한 스텁 아웃 함수를 만듭니다. 개체 또는 컨트롤에서 기존의 형식 라이브러리에 있는 현재 인터페이스에만 추가할 수 있습니다. 인터페이스를 추가할 클래스를 구현 해야 또한는 [BEGIN_COM_MAP](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333) 매크로 프로젝트 특성을 사용 하는 경우에 있어야 하거나는 `coclass` 특성입니다.  
  
 두 가지 방법 중 하나에 사용자 컨트롤에 새 인터페이스를 추가할 수 있습니다: 수동으로 또는 코드 마법사를 사용 하 여 클래스 뷰에서 합니다.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>기존 개체 또는 컨트롤에 인터페이스를 추가 하려면 클래스 뷰에서 코드 마법사를 사용 하 여  
  
1.  [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), 컨트롤의 클래스 이름을 마우스 오른쪽 단추로 클릭 합니다. 모든 권한 또는 합성 컨트롤 또는 기타 컨트롤 클래스 BEGIN_COM_MAP 매크로 헤더 파일에 구현 하는 예를 들어 있습니다.  
  
2.  바로 가기 메뉴를 클릭 하 여 **추가**를 클릭 하 고 **인터페이스 구현**합니다.  
  
3.  구현 하는 인터페이스를 선택 된 [인터페이스 구현 마법사](../../ide/implement-interface-wizard.md)합니다. 인터페이스는 사용 가능한 형식 라이브러리에 없는 경우 다음 추가 해야 수동으로.idl 파일입니다.  
  
### <a name="to-add-a-new-interface-manually"></a>새 인터페이스를 수동으로 추가 하려면  
  
1.  .Idl 파일에 새 인터페이스의 정의 추가 합니다.  
  
2.  개체 또는 컨트롤 인터페이스에서 파생 됩니다.  
  
3.  새 [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) 인터페이스에 대 한 프로젝트 특성을 사용 하는 경우 추가 또는 `coclass` 특성입니다.  
  
4.  인터페이스에서 메서드를 구현 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)


