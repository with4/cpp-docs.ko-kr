---
title: "ATL 프로젝트에 대한 컴파일러 최적화 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.optimization"
  - "vc.appwiz.ATL.vtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 컴파일러 최적화"
  - "ATL_DISABLE_NO_VTABLE 매크로"
  - "ATL_NO_VTABLE 매크로"
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL 프로젝트에 대한 컴파일러 최적화 지정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본적으로 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)는 ATL\_NO\_VTABLE 매크로를 사용하여 다음과 같이 새 클래스를 생성합니다.  
  
```  
class ATL_NO_VTABLE CProjName  
{  
   ...  
};  
```  
  
 그런 다음 ATL은 다음과 같이 \_ATL\_NO\_VTABLE을 정의합니다.  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
   #define ATL_NO_VTABLE  
#else  
   #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 \_ATL\_DISABLE\_NO\_VTABLE을 정의하지 않으면 ATL\_NO\_VTABLE 매크로가 `declspec(novtable)`으로 확장됩니다.  클래스 선언에서 `declspec(novtable)`을 사용하여 클래스 생성자와 소멸자에서 vtable 포인터가 초기화되지 않게 합니다.  프로젝트를 빌드할 때 링커는 vtable과 vtable이 가리키는 모든 함수를 제거합니다.  
  
 ATL\_NO\_VTABLE, 결과적으로 `declspec(novtable)`은 직접 만들 수 없는 기본 클래스와 함께 사용해야 합니다.  `declspec(novtable)`를 프로젝트에서 가장 많이 파생되는 클래스와 함께 사용해서는 안 됩니다. 대개 [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md) 또는 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)인 이 클래스는 프로젝트의 vtable 포인터를 초기화하기 때문입니다.  
  
 `declspec(novtable)`을 사용하는 개체의 생성자에서 가상 함수를 호출해서는 안 됩니다.  그러한 함수 호출은 [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md) 메서드로 이동해야 합니다.  
  
 `declspec(novtable)` 한정자를 사용해야 할지 여부가 확실하지 않은 경우에는 다른 모든 ATL 헤더 파일이 포함되기 전에, 모든 클래스 정의에서 ATL\_NO\_VTABLE 매크로를 제거하거나  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 ATL\_NO\_VTABLE 매크로를 전역적으로 비활성화하도록 stdafx.h에서 지정할 수 있습니다.  
  
## 참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+ 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)