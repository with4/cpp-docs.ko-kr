---
title: ATL 프로젝트에 대 한 컴파일러 최적화 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0060437613bcdd6281ce5cceb112f5fd7f470bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL 프로젝트에 대 한 컴파일러 최적화를 지정합니다.
기본적으로는 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md) ATL_NO_VTABLE 매크로 사용 하 여 새 클래스를 다음과 같이 생성 합니다.  
  
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
  
 ATL_NO_VTABLE 매크로 확장 하 여 _ATL_DISABLE_NO_VTABLE를 정의 하지 않는 경우 `declspec(novtable)`합니다. 사용 하 여 `declspec(novtable)`클래스에서 선언에서 클래스 생성자와 소멸자에서 초기화 된 vtable 포인터를 방지 합니다. 프로젝트를 빌드할 때 링커 vtable 및 vtable 가리키는 모든 함수를 제거 합니다.  
  
 ATL_NO_VTABLE를 사용 해야와 비슷하게 `declspec(novtable)`, 직접 만들 수 없거나 기본 클래스 에서만 사용 합니다. 사용 하지 않아야 `declspec(novtable)` 프로젝트에서 가장 많이 파생 된 클래스와 때문에이 클래스 (일반적으로 [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), 또는 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) 프로젝트에 대 한 vtable 포인터를 초기화합니다.  
  
 가상 함수를 사용 하는 모든 개체의 생성자에서 호출 해야 `declspec(novtable)`합니다. 해당 호출을 이동 해야는 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) 메서드.  

  
 사용 해야 할지 확실 하지 않은 경우는 `declspec(novtable)` 한정자를 모든 클래스 정의에서 ATL_NO_VTABLE 매크로 제거 하거나 지정 하 여 전역적으로 비활성화할 수 있습니다  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 stdafx.h에서 다른 모든 ATL 하기 전에 헤더 파일이 포함 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)

