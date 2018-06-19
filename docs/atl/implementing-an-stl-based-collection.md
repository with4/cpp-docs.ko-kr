---
title: C + + 표준 라이브러리 기반 컬렉션 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a09f54598b525346a65b56a335711f114878cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359677"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C + + 표준 라이브러리 기반 컬렉션 구현
ATL은 제공 된 `ICollectionOnSTLImpl` 신속 하 게 개체에 c + + 표준 라이브러리 기반 컬렉션 인터페이스를 구현할 수 있도록 인터페이스입니다. 이 클래스의 작동 방식을 이해 하려면 간단한 예제 (아래 참조)이이 클래스를 사용 하 여 자동화 클라이언트 것을 목표로 하는 읽기 전용 컬렉션을 구현 하는 작업 합니다.  
  
 예제 코드는는 [ATLCollections 샘플](../visual-cpp-samples.md)합니다.  
  
 이 절차를 완료 하려면 다음을 수행 합니다.  
  
-   [새 단순 개체 생성](#vccongenerating_an_object)합니다.  
  
-   [IDL 파일을 편집](#vcconedit_the_idl) 생성 된 인터페이스에 대 한 합니다.  
  
-   [5 개의 typedefs 만들기](#vcconstorage_and_exposure_typedefs) 컬렉션 항목이 저장 되는 방법 및 COM 인터페이스를 통해 클라이언트에 노출 될 방법을 설명 하는 합니다.  
  
-   [정책 클래스 복사본에 대 한 두 개의 typedefs 만들기](#vcconcopy_classes)합니다.  
  
-   [컬렉션 및 열거자 구현에 대 한 형식 정의 만들](#vcconenumeration_and_collection)합니다.  
  
-   [컬렉션 형식 정의 사용 하는 마법사에서 생성 된 c + + 코드 편집](#vcconedit_the_generated_code)합니다.  
  
-   [컬렉션을 채우는 코드를 추가](#vcconpopulate_the_collection)합니다.  
  
##  <a name="vccongenerating_an_object"></a> 새 단순 개체를 생성합니다.  
 응용 프로그램 설정에서 특성 상자 선택이 취소 되도록 새 프로젝트를 만듭니다. ATL 클래스 추가 대화 상자를 사용 하 고 간단한 개체를 생성 하려면 단순 개체 마법사 추가 호출 `Words`합니다. 이중 인터페이스 호출 했는지 확인 `IWords` 생성 됩니다. 생성된 된 클래스의 개체 (문자열) 단어의 컬렉션을 나타내는 데 사용 됩니다.  
  
##  <a name="vcconedit_the_idl"></a> IDL 파일을 편집  
 이제 IDL 파일을 열고 세 가지 속성을 설정 하는 데 필요한 추가 `IWords` 아래와 같이 읽기 전용 컬렉션 인터페이스에:  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]  
  
 자동화 클라이언트 염두에서에 두고 설계 하는 읽기 전용 컬렉션 인터페이스 하기 위한 표준 형식입니다. 이 인터페이스 정의에 번호가 매겨진된 주석 아래에 의견에 해당합니다.  
  
1.  자동화 클라이언트 액세스 하기 때문에 컬렉션 인터페이스는 일반적으로 이중는 `_NewEnum` 속성을 통해 **idispatch:: Invoke**합니다. 그러나 자동화 클라이언트 이중 인터페이스 dispinterface 보다 더 자주 사용 되므로 나머지 메서드는 vtable 통해 액세스할 수 있습니다.  
  
2.  이중 인터페이스 또는 dispinterface 되지 런타임 시 확장 되도록 하는 경우 (즉, 없습니다 제공한 추가 메서드 또는 속성을 통해 **idispatch:: Invoke**)를 적용 해야는 **nonextensible** 특성을 정의 합니다. 이 특성에는 자동화 클라이언트를 컴파일 타임에는 전체 코드 확인을 수행할 수 있습니다. 이 경우 인터페이스를 확장 되어야 합니다.  
  
3.  자동화 클라이언트에서이 속성을 사용 하려면 올바른 DISPID 유용 합니다. (하나만 밑줄에는 **DISPID_NEWENUM**.)  
  
4.  경우 DISPID 변수로 값을 제공할 수 있습니다는 **항목** 속성입니다. 그러나 **항목** 일반적으로 사용 하 여 **DISPID_VALUE** 를 컬렉션의 기본 속성을 확인 합니다. 따라서 자동화 클라이언트를 속성을 명시적으로 이름을 지정 하지 않고 참조할 수 있습니다.  
  
5.  반환 값에 사용 되는 데이터 형식에서 **항목** 속성은 COM 클라이언트에 관한 관련해 서는 컬렉션에 저장 된 항목의 형식입니다. 인터페이스 문자열을 반환 하는 표준 COM 문자열 형식을 사용 해야 하므로 `BSTR`합니다. 저장할 수 있습니다 데이터를 다른 형식으로 내부적으로 바로 확인할 수 있습니다.  
  
6.  DISPID를 사용 하는 값은 **Count** 속성은 완전히 임의의 합니다. 이 속성에 대 한 표준 DISPID 되지 않습니다.  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> 저장 및 노출 하는 것에 대 한 형식 정의 만들기  
 컬렉션 인터페이스에서 정의 되 면 어떻게 데이터를 저장 되 고 열거자를 통해 데이터는 노출 하는 방법을 결정 해야 합니다.  
  
 이러한 질문에 답변 다양 한 새로 만든된 클래스에 대 한 헤더 파일의 맨 위 근처에 추가할 수 있는 형식 정의의 형태로 제공 될 수 있습니다.  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]  
  
 이 경우 데이터를 저장 하는 한 **std:: vector** 의 **std:: string**s입니다. **std:: vector** 는 관리 되는 배열 처럼 동작 하는 c + + 표준 라이브러리 컨테이너 클래스입니다. **std:: string** c + + 표준 라이브러리의 문자열 클래스입니다. 이러한 클래스 쉽게 문자열의 컬렉션을 사용 합니다.  
  
 열거자에서 반환 된 Visual Basic 지원이이 인터페이스의 성공에 필수적 이므로 `_NewEnum` 속성을 지원 해야 합니다는 **IEnumVARIANT** 인터페이스입니다. Visual Basic에서 인식 하는 유일한 열거자 인터페이스입니다.  
  
##  <a name="vcconcopy_classes"></a> 복사 정책 클래스에 대 한 형식 정의 만들기  
 지금까지 만든 typedefs 추가로 열거자 및 컬렉션에 사용 될 복사 클래스에 대 한 형식 정의 만드는 데 필요한 모든 정보를 제공 합니다.  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]  
  
 이 예제에서는 사용자 지정을 사용할 수 있습니다 `GenericCopy` VCUE_Copy.h 및에서 VCUE_CopyString.h에 정의 된 클래스는 [ATLCollections](../visual-cpp-samples.md) 샘플. 다른 코드에서이 클래스를 사용할 수 있지만 추가의 특수화를 정의 해야 할 수 있습니다 `GenericCopy` 사용자 지정 컬렉션에 사용 되는 데이터 형식을 지원 하도록 합니다. 자세한 내용은 참조 [ATL 복사 정책 클래스](../atl/atl-copy-policy-classes.md)합니다.  
  
##  <a name="vcconenumeration_and_collection"></a> 열거형 및 컬렉션에 대 한 형식 정의 만들기  
 이제 모든 템플릿 매개 변수 특수화 하는 데 필요한는 `CComEnumOnSTL` 및 `ICollectionOnSTLImpl` 이러한 상황에 대 한 클래스 형식 정의의 형태로 제공 되었습니다. 특수화의 사용을 단순화 하려면 아래와 같이 두 개 더 많은 형식 정의 만듭니다.  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]  
  
 이제 `CollectionType` 의 특수화에 대 한 동의어 `ICollectionOnSTLImpl` 구현 하는 `IWords` 인터페이스 앞에서 정의한 및 지 원하는 열거자를 제공 합니다. **IEnumVARIANT**합니다.  
  
##  <a name="vcconedit_the_generated_code"></a> 마법사에서 생성 된 코드를 편집합니다.  
 파생 해야 하는 이제 `CWords` 나타내는 인터페이스 구현에서는 `CollectionType` typedef 대신 `IWords`다음과 같이:  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a> 컬렉션을 채우는 코드를 추가 합니다.  
 남아 있는 유일한 항목은 데이터를 사용 하 여 벡터를 채우는 것입니다. 이 간단한 예제에서는 컬렉션 클래스에 대 한 생성자에 몇 가지 단어를 추가할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]  
  
 이제 사용자가 선택한 클라이언트에서 코드를 테스트할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections 샘플](../visual-cpp-samples.md)   
 [ATL 복사 정책 클래스](../atl/atl-copy-policy-classes.md)

