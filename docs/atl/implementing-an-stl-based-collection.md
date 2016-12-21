---
title: "Implementing an STL-Based Collection | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl interface"
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing an STL-Based Collection
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL에서 제공 된 `ICollectionOnSTLImpl` 개체에서 STL 표준 템플릿 라이브러리 기반 컬렉션 인터페이스를 신속 하 게 구현할 수 있도록 하는 인터페이스.  이 클래스의 작동 방식을 이해 하려면이 클래스를 사용 하 여 자동화 클라이언트를 위한 읽기 전용 컬렉션을 구현 하는 간단한 예제 \(아래\)를 통해 작동 합니다.  
  
 샘플 코드에서 되는  [ATLCollections 샘플에서](../top/visual-cpp-samples.md)는.  
  
 이 절차를 완료 하려면 다음을 수행할 수 있습니다.  
  
-   [새로운 단순 개체 생성](#vccongenerating_an_object).  
  
-   [IDL 파일을 편집](#vcconedit_the_idl) 생성 된 인터페이스에 대 한.  
  
-   [5 형식 정의 만드는](#vcconstorage_and_exposure_typedefs) 컬렉션의 항목을 저장 하는 방법을 및 어떻게 이러한 COM 인터페이스를 통해 클라이언트에 노출 됩니다.  
  
-   [두 형식 정의를 복사 정책 클래스 만들기](#vcconcopy_classes).  
  
-   [컬렉션 및 열거자 구현에 대 한 형식 정의 만들기](#vcconenumeration_and_collection).  
  
-   [컬렉션 형식 정의 사용 하는 마법사에서 생성 된 C\+\+ 코드를 편집](#vcconedit_the_generated_code).  
  
-   [컬렉션을 채우는 코드를 추가 합니다.](#vcconpopulate_the_collection).  
  
##  <a name="vccongenerating_an_object"></a> 새로운 단순 개체 생성  
 응용 프로그램 설정의 특성 상자가 선택 해제 되어 있는지 확인 하는 새 프로젝트를 만듭니다.  ATL 클래스 추가 대화 상자를 사용 하 고 간단한 개체 단순 개체 생성 마법사에 추가 `Words`.  이중 인터페이스 호출 하도록 `IWords` 생성 됩니다.  생성 된 클래스의 개체 단어 \(문자열\)의 컬렉션을 나타내는 데 사용 됩니다.  
  
##  <a name="vcconedit_the_idl"></a> IDL 파일 편집  
 이제 IDL 파일을 열고 세 가지 속성을 설정 하는 데 필요한 추가 `IWords` 에 있는 읽기 전용 컬렉션 인터페이스를 아래와 같이 합니다.  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/CPP/implementing-an-stl-based-collection_1.idl)]  
  
 이 자동화 클라이언트를 고려 하 여 디자인 하는 읽기 전용 컬렉션 인터페이스에 대 한 표준 양식입니다.  이 인터페이스 정의에서 번호가 매겨진된 주석에 아래 의견에 해당합니다.  
  
1.  컬렉션 인터페이스 이므로 일반적으로 이중 자동화 클라이언트에 액세스 하는 `_NewEnum` 속성을 통해  **IDispatch::Invoke**.  그러나 이중 인터페이스 dispinterfaces를 선호 하므로 자동화 클라이언트 vtable 통해 나머지 메서드에 액세스할 수 있습니다.  
  
2.  런타임에 인터페이스를 이중 또는 dispinterface 연장 되지 않습니다 경우 \(즉, 추가 메서드나 속성을 통해 제공 되지 않습니다  **IDispatch::Invoke**\)를 적용 해야는  **nonextensible** 특성을 정의 합니다.  이 특성은 자동화 클라이언트가 전체 코드를 확인 하는 컴파일 타임에 수행할 수 있습니다.  이 경우 인터페이스 확장 되어야 합니다.  
  
3.  올바른 DISPID 자동화 클라이언트는이 속성을 사용할 수 있도록 하려는 경우에 중요 합니다.  \(하나의 밑줄에는  **DISPID\_NEWENUM**.\)  
  
4.  Dispid 값으로 값을 제공할 수 있는  **항목** 속성.  그러나  **항목** 일반적으로 사용 하 여  **DISPID\_VALUE** 이 컬렉션의 기본 속성을 확인 합니다.  이 속성을 명시적으로 명명 않고 참조에 자동화 클라이언트가 있습니다.  
  
5.  데이터 형식에 대 한 반환 값을 사용 하는  **항목** 속성은 COM 클라이언트는 관심이 서 컬렉션에 저장 된 항목의 형식입니다.  표준 COM 문자열 형식을 사용 해야 하므로 인터페이스 문자열 반환 `BSTR`.  곧 확인 하겠지만 내부적으로 데이터를 다른 형식으로 저장할 수 있습니다.  
  
6.  DISPID를 사용 하는 값은  **수** 속성이 달라 집니다.  이 속성에 대 한 없는 표준 DISPID입니다.  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> 저장 및 노출에 대 한 형식 정의 만들기  
 컬렉션 인터페이스를 정의한 후 데이터는 어떻게 저장 됩니다, 열거자를 통해 데이터를 노출 하는 방법을 결정 해야 합니다.  
  
 새로 만든된 클래스의 헤더 파일 위쪽에 추가할 수 있습니다 형식 정의의 여러 형태로 이러한 질문에 대답을 제공할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/CPP/implementing-an-stl-based-collection_2.h)]  
  
 이 경우 데이터를 저장할는  **상의** 의  **std::string**s.  **상의** 는 관리 되는 배열 처럼 동작 하며는 STL 컨테이너 클래스입니다.  **std::string** 표준 C\+\+ 라이브러리 문자열 클래스입니다.  이러한 클래스는 문자열의 컬렉션을 사용할 수 쉽게 있습니다.  
  
 Visual Basic 지원이이 인터페이스의 성공에 필수적 이므로 열거자가 반환 된 `_NewEnum` 속성을 지원 해야는  **IEnumVARIANT** 인터페이스.  이 Visual Basic 이해 하는 유일한 열거자 인터페이스입니다.  
  
##  <a name="vcconcopy_classes"></a> 복사 정책 클래스에 대 한 형식 정의 만들기  
 지금까지 만든 형식 정의 더 열거자 및 컬렉션에서 사용 되는 복사 클래스 형식 정의 만드는 데 필요한 모든 정보를 제공 합니다.  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/CPP/implementing-an-stl-based-collection_3.h)]  
  
 이 예제에서는 사용자 지정을 사용할 수 있습니다 `GenericCopy` vcue\_copy.h와 vcue\_copystring.h에서 정의 하는 클래스는  [ATLCollections](../top/visual-cpp-samples.md) 샘플.  다른 코드에서이 클래스를 사용 하지만 특수화를 추가로 정의 해야 `GenericCopy` 컬렉션에 사용 되는 데이터 형식을 지원 합니다.  자세한 내용은  [ATL 복사 정책 클래스](../atl/atl-copy-policy-classes.md).  
  
##  <a name="vcconenumeration_and_collection"></a> 열거 하 고 컬렉션에 대 한 형식 정의 만들기  
 이제 모든 템플릿 매개 변수가 필요한 특수화는 `CComEnumOnSTL` 및 `ICollectionOnSTLImpl` 이 상황에 대 한 클래스 형식 정의 형태로 제공 되었습니다.  특수화의 사용을 단순화 하기 위해 아래와 같이 두 typedef를 만듭니다.  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/CPP/implementing-an-stl-based-collection_4.h)]  
  
 이제 `CollectionType` 의 특수화는 동일 `ICollectionOnSTLImpl` 를 구현 하는 `IWords` 인터페이스 정의 및 해당 지원 열거자를 제공  **IEnumVARIANT**.  
  
##  <a name="vcconedit_the_generated_code"></a> 마법사에서 생성 된 코드를 편집합니다.  
 파생 되어야 이제 `CWords` 인터페이스 구현을 나타내는에서 `CollectionType` typedef 아니라 `IWords`, 아래와 같이:  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/CPP/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a> 컬렉션을 채우는 코드를 추가 합니다.  
 남아 있는 유일 벡터 데이터로 채우는 것입니다.  이 간단한 예제에서는 몇 개의 단어 컬렉션 클래스의 생성자에 추가할 수 있습니다.  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/CPP/implementing-an-stl-based-collection_6.h)]  
  
 이제 선택한 클라이언트에 코드를 테스트할 수 있습니다.  
  
## 참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections 샘플](../top/visual-cpp-samples.md)   
 [ATL Copy Policy Classes](../atl/atl-copy-policy-classes.md)