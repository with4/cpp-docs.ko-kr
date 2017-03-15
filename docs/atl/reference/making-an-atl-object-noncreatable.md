---
title: "ATL 개체 수 없도록 설정 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: b812c2d4bfeb0663d62051c05829f25dc7139faf
ms.lasthandoff: 02/24/2017

---
# <a name="making-an-atl-object-noncreatable"></a>ATL 개체 수 없도록 설정 만들기
클라이언트 개체를 직접 만들 수 없습니다 있도록 ATL 기반 COM 개체의 특성을 변경할 수 있습니다. 이 경우 개체는 다른 개체의 메서드 호출을 통해 반환 되지 않고 됩니다 직접 만든.  
  
### <a name="to-make-an-object-noncreatable"></a>개체 수 없도록 설정 하려면  
  
1.  제거는 [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) 개체입니다. 개체를 생성할 수 없는 아니라 등록할 컨트롤을 사용 하도록 하려는 경우 교체 된 OBJECT_ENTRY_AUTO [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1)합니다.  
  
2.  추가 된 [noncreatable](../../windows/noncreatable.md) .idl 파일에서 coclass 하는 특성입니다. 예:  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)


