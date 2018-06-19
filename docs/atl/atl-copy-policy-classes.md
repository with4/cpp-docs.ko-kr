---
title: ATL 복사 정책 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34b9ed5dca45633a5ab980d38b8a7cda151f5dc7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358529"
---
# <a name="atl-copy-policy-classes"></a>ATL 복사 정책 클래스
복사 정책 클래스는 [유틸리티 클래스가](../atl/utility-classes.md) 초기화 하는 데 사용, 복사 및 데이터를 삭제 합니다. 복사 정책 클래스를 사용 하 여 모든 유형의 데이터에 대 한 복사 의미를 정의 하 고 다른 데이터 형식 간의 변환을 정의할 수 있습니다.  
  
 ATL 사용 하 여 복사본 정책 클래스 다음 서식 파일의 해당 구현에서:  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 복사 하거나 템플릿 인수로 전달 될 수 있는 복사 정책 클래스의 데이터를 변환 하는 데 필요한 정보를 캡슐화 하 여 이러한 클래스의 극단적인 재사용성에 대 한 ATL 개발자가 제공 합니다. 예를 들어 임의의 데이터 형식을 사용 하 여 컬렉션을 구현 해야 할 경우 제공 하기만 하면 되는 적절 한 복사본 정책. 컬렉션을 구현 하는 코드를 터치 않아도 됩니다.  
  
## <a name="definition"></a>정의  
 정의 다음과 같은 정적 함수를 제공 하는 클래스는 복사 정책 클래스:  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 형식을 바꿀 수 `DestinationType` 및 *SourceType* 각 복사본 정책에 대 한 임의의 데이터 형식입니다.  
  
> [!NOTE]
>  임의의 데이터 형식에 대 한 복사 정책 클래스를 정의할 수도 있지만 ATL 코드의 클래스를 사용 하 여 의미 있는 형식 제한 해야 합니다. 예를 들어 경우 복사 정책을 사용 하 여 클래스와 ATL의 컬렉션 또는 열거자 구현 `DestinationType` COM 인터페이스 메서드에 매개 변수로 사용할 수 있는 형식 이어야 합니다.  
  
 사용 하 여 **init** 데이터를 초기화 **복사** 데이터를 복사 하 고 **destroy** 는 데이터를 합니다. 초기화의 정확한 의미, 복사 및 소멸은 복사 정책 클래스의 도메인 및 관련 된 데이터 형식에 따라 달라 집니다.  
  
 사용 방법과 복사 정책 클래스의 구현에는 두 가지 요구 사항이 있습니다.  
  
-   첫 번째 매개 변수를 **복사** 만 사용 하 여 이전에 초기화 한 데이터에 대 한 포인터를 받아야 **init**합니다.  
  
-   **destroy** 만 사용 하 여 이전에 초기화 한 데이터에 대 한 포인터를 받아야 **init** 또는 통해 복사 **복사**합니다.  
  
## <a name="standard-implementations"></a>표준 구현  
 ATL은 두 복사 정책 클래스의 형태로 제공는 **_Copy** 및 **_CopyInterface** 템플릿 클래스:  
  
-   **_Copy** 만 복사 유형이 같은 클래스를 사용 하면 (데이터 형식 간의 변환 하지) 모두 지정할 수 하나의 템플릿 매개 변수만 제공 하므로 `DestinationType` 및 *SourceType*합니다. 이 서식 파일의 제네릭 구현을 초기화 또는 소멸 코드가 없는 및 사용 하 여 `memcpy` 데이터를 복사 합니다. ATL은 또한의 특수화 제공 **_Copy** 에 대 한 **VARIANT**, `LPOLESTR`, **OLEVERB**, 및 **CONNECTDATA** 데이터 형식입니다.  
  
-   **_CopyInterface** 클래스 표준 규칙에 COM 인터페이스 포인터를 복사 하기 위한 구현을 제공 합니다. 다시 한 번이 클래스를 사용 하면만 동종 복사는 단순 할당 및에 대 한 호출을 사용 하므로 `AddRef` 복사를 수행 합니다.  
  
## <a name="custom-implementations"></a>사용자 지정 구현  
 일반적으로 다른 유형의 (즉, 데이터 형식 간 변환)를 복사 하기 위한 고유한 복사본 정책 클래스를 정의 해야 합니다. 몇 가지 예제 사용자 지정 복사본 정책 클래스는 VCUE_Copy.h 및 VCUE_CopyString.h에서 파일을 볼는 [ATLCollections](../visual-cpp-samples.md) 샘플. 이 파일은 두 개의 템플릿 복사 정책 클래스 포함 `GenericCopy` 및 `MapCopy`, 더하기 특수화의 숫자가 `GenericCopy` 서로 다른 데이터 형식에 대 한 합니다.  
  
### <a name="genericcopy"></a>GenericCopy  
 `GenericCopy` 지정할 수 있습니다는 *SourceType* 및 `DestinationType` 템플릿 인수로 사용 합니다. 다음은 가장 일반적인 형태의 `GenericCopy` VCUE_Copy.h에서 클래스:  
  
 [!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]  
  
 이 클래스의 다음 특수화 VCUE_Copy.h에도 포함 되어: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`합니다. VCUE_CopyString.h 포함에서 복사에 대 한 특수화 **std:: string**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, 및 `GenericCopy<BSTR, std::string>`합니다. 높일 수 `GenericCopy` 추가 자신만의 특수화를 제공 하 여 합니다.  
  
### <a name="mapcopy"></a>MapCopy  
 `MapCopy` 이므로 데이터가 저장 되 고 대상 유형 맵의 형식을 지정할 수 있습니다 데이터를 복사 하는 c + + 표준 라이브러리 스타일 map에 저장 되어 있다고 가정 합니다. 클래스의 구현을 사용 하 여 제공한 typedef는 *MapType* 클래스 원본 데이터의 형식을 결정 하 고 적절 한 호출 `GenericCopy` 클래스입니다. 이 클래스의 없음 특수화가 필요 합니다.  
  
 [!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리 기반 컬렉션 구현](../atl/implementing-an-stl-based-collection.md)   
 [ATLCollections 샘플](../visual-cpp-samples.md)

