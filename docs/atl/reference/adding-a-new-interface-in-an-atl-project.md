---
title: "ATL 프로젝트에 새 인터페이스를 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.interface
dev_langs: C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21aeda51a917bcb48b16ff8f9c2bc505adc18f1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL 프로젝트에 새 인터페이스 추가
개체 또는 컨트롤에는 인터페이스를 추가 하면 해당 인터페이스의 각 메서드에 대 한 스텁 아웃 함수를 만듭니다. 개체 또는 컨트롤에서 현재 기존의 형식 라이브러리에서 찾은 인터페이스만 추가할 수 있습니다. 또한 인터페이스를 추가할 클래스 구현 해야 합니다는 [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) 매크로 프로젝트 특성을 사용 하는 경우에 있어야 하거나는 `coclass` 특성입니다.  
  
 두 가지 방법 중 하나에 사용자 컨트롤에 새 인터페이스를 추가할 수 있습니다: 수동으로 또는 코드 마법사를 사용 하 여 클래스 뷰에서 합니다.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>기존 개체 또는 컨트롤에 인터페이스를 추가 하려면 클래스 보기에서 코드 마법사를 사용 하려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)를 컨트롤의 클래스 이름을 마우스 오른쪽 단추로 클릭 합니다. 예를 들어, 모든 권한 또는 합성 컨트롤 또는 BEGIN_COM_MAP 매크로 헤더 파일에 구현 하는 다른 컨트롤 클래스입니다.  
  
2.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **인터페이스 구현**합니다.  
  
3.  선택 인터페이스에서 구현 하는 [인터페이스 구현 마법사](../../ide/implement-interface-wizard.md)합니다. 인터페이스 사용 가능한 모든 typelib에 없는 경우 다음 추가 해야 수동으로.idl 파일입니다.  
  
### <a name="to-add-a-new-interface-manually"></a>새 인터페이스를 수동으로 추가 하려면  
  
1.  .Idl 파일에 새 인터페이스의 정의 추가 합니다.  
  
2.  개체 또는 인터페이스에서 컨트롤 파생 됩니다.  
  
3.  새 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 인터페이스에 대 한 프로젝트 특성을 사용 하는 경우 추가 또는 `coclass` 특성입니다.  
  
4.  인터페이스에서 메서드를 구현 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)

