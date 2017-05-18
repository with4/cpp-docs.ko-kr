---
title: "ATL 프로젝트에 대 한 컴파일러 최적화를 지정 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: abdad4367e75c1971ba5d11af1a60992d1bb3dd4
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL 프로젝트에 대 한 컴파일러 최적화를 지정합니다.
기본적으로는 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md) ATL_NO_VTABLE 매크로 사용 하는 새 클래스를 다음과 같이 생성 합니다.  
  
```  
class ATL_NO_VTABLE CProjName  
{  
 ...  
};  
```  
  
 ATL 다음 _ATL_NO_VTABLE를 다음과 같이 정의합니다.  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
 #define ATL_NO_VTABLE  
#else  
 #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 ATL_NO_VTABLE 매크로 확장 하 여 _ATL_DISABLE_NO_VTABLE를 정의 하지 않는 경우 `declspec(novtable)`합니다. 사용 하 여 `declspec(novtable)`vtable 포인터를 클래스 생성자와 소멸자에서 초기화할 선언 클래스에서 방지 합니다. 프로젝트를 빌드할 때 링커 vtable 및 vtable 가리키는 모든 함수를 제거 합니다.  
  
 ATL_NO_VTABLE를 사용 해야 하므로 `declspec(novtable)`, 직접 만들 수 없거나 지만 기본 클래스와 함께 합니다. 사용 하면 안 `declspec(novtable)` 프로젝트에서 가장 많이 파생 된 클래스를 사용 하기 때문에이 클래스 (일반적으로 [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), 또는 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) 프로젝트에 대 한 vtable 포인터를 초기화 합니다.  
  
 가상 함수를 사용 하는 모든 개체의 생성자에서 호출 해야 `declspec(novtable)`합니다. 에 대 한 호출을 이동 해야는 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) 메서드.  

  
 사용 해야 하는지 확실 하지 않은 경우는 `declspec(novtable)` 한정자를 모든 클래스 정의에서 ATL_NO_VTABLE 매크로 제거 하거나 지정 하 여 전체적으로 비활성화할 수 있습니다  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 stdafx.h에서 전에 다른 모든 ATL 헤더 파일이 포함 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)


