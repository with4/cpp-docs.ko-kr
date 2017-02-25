---
title: "ATL Copy Policy Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_Copy class"
  - "_CopyInterface class"
  - "클래스[C++], copy policy"
  - "copy policy classes [C++]"
  - "데이터[C++], ATL"
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL Copy Policy Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

복사 정책 클래스는  [유틸리티 클래스](../atl/utility-classes.md) 를 초기화 하는 데 사용, 복사 및 데이터를 삭제 합니다.  복사 정책 클래스 복사 의미 모든 종류의 데이터를 정의 하 고 다른 데이터 형식 간의 변환을 정의할 수 있습니다.  
  
 ATL 사용 복사 정책 클래스의 구현 과정은 다음과 같은 템플릿을.  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 복사 또는 데이터 템플릿 인수로 전달할 수 있는 복사 정책 클래스를 변환 하는 데 필요한 정보를 캡슐화 하 여 ATL 개발자 익스트림 애플리케이션에서의 이러한 클래스를 제공 합니다.  예를 들어, 임의의 데이터 형식을 사용 하 여 컬렉션을 구현 하는 경우 제공 하는 데 필요한 모든입니다 적절 한 복사 정책. 컬렉션을 구현 하는 코드를 수정 하는 되지 않습니다.  
  
## 정의  
 기본적으로 다음 정적 함수를 제공 하는 클래스는 복사 정책 클래스가입니다.  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 종류를 바꿀 수 있습니다 `DestinationType` 및  *기존의* 임의의 데이터 형식과 복사 정책 각각에 대해.  
  
> [!NOTE]
>  복사 정책 클래스는 임의의 데이터 형식에 대해 정의할 수 있지만 클래스 ATL 코드에서 사용을 감지 하는 형식을 제한 해야 합니다.  예를 들어 때 복사 정책 클래스 ATL의 컬렉션 또는 열거자 구현에 `DestinationType` COM 인터페이스 메서드 매개 변수로 사용할 수 있는 형식 이어야 합니다.  
  
 사용  **초기화** 데이터를 초기화 하  **복사** 데이터를 복사 하 고  **파괴** 데이터를 제거 합니다.  정확한 의미는 초기화, 복사 및 소멸 복사 정책 클래스의 도메인 및 관련된 데이터 형식에 따라 달라 집니다.  
  
 사용 및 복사 정책 클래스의 구현에서 두 가지 요구 사항이 있습니다.  
  
-   첫 번째 매개 변수를  **복사** 를 사용 하 여 이전에 초기화 한 데이터에 대 한 포인터를 받아야만  **초기화**.  
  
-   **파괴** 만 사용 하 여 이전에 초기화 한 데이터에 대 한 포인터를 받아야  **초기화** 또는 복사를 통해  **복사**.  
  
## 표준 구현  
 ATL 두 복사 정책 클래스의 형태로 제공 된  **\_Copy** 및  **\_CopyInterface** 템플릿 클래스:  
  
-   **\_Copy** 클래스 있습니다만 복사 동종 \(않습니다: 데이터 형식 간의 변환\) 단일 템플릿 매개 변수가 모두 지정 하 여만 제공 하므로 `DestinationType` 및  *기존의*.  이 서식 파일의 일반 구현을 초기화 또는 소멸 코드가 없습니다 및 사용 `memcpy` 데이터를 복사 합니다.  ATL에서는 특수화의  **\_Copy** 의  **변형**, `LPOLESTR`,  **OLEVERB**, 및  **CONNECTDATA** 데이터 형식.  
  
-   **\_CopyInterface** 클래스는 표준 COM 규칙을 준수 하는 인터페이스 포인터를 복사에 대 한 구현을 제공 합니다.  단순 할당 및 호출을 사용 하도록 다시 한 번이 클래스 동종 복사만 수 `AddRef` 복사할 수 있습니다.  
  
## 사용자 지정 구현  
 일반적으로 이기종 \(데이터 형식 간의 변환\) 복사에 대 한 고유한 복사 정책 클래스를 정의 해야 합니다.  몇 가지 사용자 지정 복사 정책 클래스는 vcue\_copy.h와 vcue\_copystring.h에서 파일 확인은  [ATLCollections](../top/visual-cpp-samples.md) 샘플.  두 템플릿 복사 정책 클래스이 파일 포함 `GenericCopy` 및 `MapCopy`, 수 중의 특수화 `GenericCopy` 다른 데이터 형식에 대 한.  
  
### GenericCopy  
 `GenericCopy`지정할 수 있는  *기존의* 및 `DestinationType` 템플릿 인수로.  다음은 가장 일반적인 형태는 `GenericCopy` VCUE\_Copy.h 클래스:  
  
 [!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/CPP/atl-copy-policy-classes_1.h)]  
  
 Vcue\_copy.h도 다음이 클래스의 특수화에 포함: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`.  Vcue\_copystring.h에서 복사 특수화 포함  **std::string**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, 및 `GenericCopy<BSTR, std::string>`.  강화 수 `GenericCopy` 특수화를 추가로 제공 합니다.  
  
### MapCopy  
 `MapCopy`맵 데이터를 저장 하 고 대상 입력 유형을 지정할 수 있도록 데이터를 복사 하 고 STL 스타일 맵에 저장할 수 있다고 가정 합니다.  구현 클래스의 방금 제공한 형식 정의 사용 하는  *MapType* 원본 데이터의 형식을 확인 하 고 적절 한 호출 클래스 `GenericCopy` 클래스.  없음이 클래스의 특수화에 필요 합니다.  
  
 [!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/CPP/atl-copy-policy-classes_2.h)]  
  
## 참고 항목  
 [Implementing an STL\-Based Collection](../atl/implementing-an-stl-based-collection.md)   
 [ATLCollections 샘플](../top/visual-cpp-samples.md)