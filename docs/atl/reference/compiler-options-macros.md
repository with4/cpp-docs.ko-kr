---
title: "Compiler Options Macros | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컴파일러 옵션, 매크로"
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Compiler Options Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 매크로 특정 컴파일러 기능을 제어 합니다.  
  
|||  
|-|-|  
|[\_ATL\_ALL\_WARNINGS](../Topic/_ATL_ALL_WARNINGS.md)|오류 ATL.의 이전 버전에서 변환 된 프로젝트에 사용할 수 있는 기호|  
|[\_ATL\_APARTMENT\_THREADED](../Topic/_ATL_APARTMENT_THREADED.md)|하나 이상의 개체가 아파트 스레딩을 사용 하는 경우 정의 합니다.|  
|[\_ATL\_CSTRING\_EXPLICIT\_CONSTRUCTORS](../Topic/_ATL_CSTRING_EXPLICIT_CONSTRUCTORS.md)|수 `CString` 는 의도 하지 않은 변환을 방지 명시적 생성자입니다.|  
|[\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md)|멤버 함수에 대 한 포인터를 초기화 하는 비 표준 구문을 사용 하면 컴파일러 C4867 오류가 생성 C\+\+ 표준 준수 구문을 사용 하려면이 매크로 정의 합니다.|  
|[\_ATL\_FREE\_THREADED](../Topic/_ATL_FREE_THREADED.md)|하나 이상의 개체가 자유 또는 중립 스레딩을 사용 하는 경우 정의 합니다.|  
|[\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md)|프로젝트를 나타내는 기호 두 가지로, 자유 또는 중립 표시 된 개체를 해야 합니다.  매크로  [\_ATL\_FREE\_THREADED](../Topic/_ATL_FREE_THREADED.md) 대신 사용 해야 합니다.|  
|[\_ATL\_NO\_AUTOMATIC\_NAMESPACE](../Topic/_ATL_NO_AUTOMATIC_NAMESPACE.md)|기호는 ATL. 네임 스페이스의 기본 사용|  
|[\_ATL\_NO\_COM\_SUPPORT](../Topic/_ATL_NO_COM_SUPPORT.md)|코드 COM 관련 프로젝트를 컴파일하지 않도록 하는 기호입니다.|  
|[ATL\_NO\_VTABLE](../Topic/ATL_NO_VTABLE.md)|기호 vtable 포인터를 클래스의 생성자와 소멸자를 초기화할 수 없습니다.|  
|[ATL\_NOINLINE](../Topic/ATL_NOINLINE.md)|함수를 나타내는 기호를 인라인 하지 않습니다.|  
|[\_ATL\_SINGLE\_THREADED](../Topic/_ATL_SINGLE_THREADED.md)|모든 개체가 단일 스레딩 모델을 사용 하는 경우 정의 합니다.|  
  
## 참고 항목  
 [Macros](../../atl/reference/atl-macros.md)