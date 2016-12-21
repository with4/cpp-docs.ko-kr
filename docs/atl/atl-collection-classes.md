---
title: "ATL 컬렉션 클래스 | Microsoft Docs"
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
  - "컬렉션 클래스"
  - "컬렉션 클래스, 컬렉션 클래스 정보"
  - "컬렉션 클래스, 선택"
  - "ConstructElements 함수"
  - "CTraits 클래스"
  - "DestructElements 함수"
  - "SerializeElements 함수"
  - "traits 클래스"
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 컬렉션 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 데이터 저장 및 액세스에 대 한 다양 한 클래스를 제공 합니다.  사용 하려는 클래스 등 여러 요인에 따라 달라 집니다.  
  
-   저장할 데이터의 양  
  
-   데이터 액세스 성능 및 효율성  
  
-   키 또는 인덱스 데이터에 액세스 하는 기능  
  
-   데이터 정렬 방법  
  
-   개인 기본 설정  
  
## 소규모 컬렉션 클래스  
 ATL 적은 수의 개체를 처리 하기 위한 다음과 같은 배열 클래스를 제공합니다.  그러나 이러한 클래스 제한 고 사용 하기 위해 내부적으로 ATL에서 설계  프로그램에서 사용할 권장 되지 않습니다.  
  
|클래스|데이터 저장소 유형|  
|---------|----------------|  
|[CSimpleArray](../atl/reference/csimplearray-class.md)|적은 수의 개체를 처리 하기 위한 배열 클래스를 구현합니다.|  
|[CSimpleMap](../atl/reference/csimplemap-class.md)|적은 수의 개체를 처리 하기 위한 매핑 클래스를 구현합니다.|  
  
## 범용 컬렉션 클래스  
 다음 클래스는 배열, 목록 및 맵을 구현 및 범용 컬렉션 클래스로 제공 됩니다.  
  
|클래스|데이터 저장소 유형|  
|---------|----------------|  
|[CAtlArray](../atl/reference/catlarray-class.md)|배열을 구현합니다.|  
|[CAtlList](../atl/reference/catllist-class.md)|목록을 구현 합니다.|  
|[CAtlMap](../atl/reference/catlmap-class.md)|데이터 키 또는 값에 의해 참조 될 수 있도록 매핑 구조체를 구현 합니다.|  
|[CRBMap](../atl/reference/crbmap-class.md)|빨강, 검정 알고리즘을 사용 하 여 매핑 구조체를 구현 합니다.|  
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|빨강\-검정 multimapping 구조를 구현합니다.|  
  
 이러한 클래스 디버그 빌드에서만 사용할 때 많은 프로그래밍 오류를 잡을 수 있지만 성능 코드를 작성 해야 이러한 검사 일반 정품 빌드에서 수행 되지 않습니다.  
  
## 특수 컬렉션 클래스  
 보다 전문화 된 컬렉션 클래스도 메모리 포인터 및 인터페이스 포인터를 관리 하는 데 제공 됩니다.  
  
|클래스|목적|  
|---------|--------|  
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|스마트 포인터 배열을 구성할 때 유용한 메서드를 제공 합니다.|  
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|스마트 포인터 목록을 구성할 때 유용한 메서드를 제공 합니다.|  
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|저장소 `IUnknown` 포인터를 매개 변수로 사용 하도록 하 고 있는  [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스.|  
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|힙 포인터 목록을 구성할 때 유용한 메서드를 제공 합니다.|  
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|COM 인터페이스 포인터 배열을 구성할 때 유용한 메서드를 제공 합니다.|  
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|COM 인터페이스 포인터 목록을 구성할 때 유용한 메서드를 제공 합니다.|  
  
## 컬렉션 클래스를 선택합니다.  
 아래 표와 같이 각각 사용할 수 있는 컬렉션 클래스의 다른 성능 특성을 제공 합니다.  
  
-   2\-3 열 각 클래스의 정렬 및 특성에 액세스 합니다.  테이블에 항목이 삽입 및 삭제 된 주문 컬렉션의 순서를 결정 "주문" 이라는 용어를 의미 합니다. 이 항목의 내용을 정렬 되지는지 않습니다.  용어 "인덱스" 컬렉션에 있는 항목을 일반 배열의 항목 처럼 정수 인덱스로 검색할 수 있습니다.  
  
-   4 및 5 번 열 각 클래스의 성능에 설명 합니다.  컬렉션에 항목을 많이 삽입 해야 하는 응용 프로그램에서는 삽입 속도가 특히 중요할 수 있습니다. 다른 응용 프로그램에 대 한 조회 속도가 더 중요할 수도 있습니다.  
  
-   6 열 각 셰이프 중복 요소가 허용 되는지 여부를 설명 합니다.  
  
-   지정 된 컬렉션 클래스 작업의 성능은 컬렉션의 요소 수가 작업을 완료 하는 데 필요한 시간 간의 관계로 표현 됩니다.  요소 수가 o \(n\) 알고리즘으로 설명한 시간 하는 작업은 선형적으로 증가.  그러나 점점 덜 요소 수가 증가 하는 시간을 하는 작업은 O \(log n\) 알고리즘으로 설명 되어 있습니다.  따라서 성능이 O \(log n\) 알고리즘을 o \(n\) 알고리즘을 요소 수가으로 점점 더 좋아집니다.  
  
### 컬렉션 모양 특징  
  
|모양|주문?|인덱스?|삽입 된<br /><br /> 요소|검색에 대 한<br /><br /> 지정 된 요소|중복됨<br /><br /> 요소?|  
|--------|---------|----------|-----------------|-------------------------|-----------------|  
|List|예|아니요|빠른 \(일정 한 시간\)|느린 o \(n\)|예|  
|배열|예|Int \(일정 한 시간\)에서|O \(n\) 끝에는 일정 한 시간에 삽입 하는 경우를 제외 하 고 느리게|느린 o \(n\)|예|  
|맵|아니요|키에 의해 \(일정 한 시간\)|빠른 \(일정 한 시간\)|빠른 \(일정 한 시간\)|\(키\) 예 \(값\)|  
|빨강, 검정 지도|예 \(키로\)|키에 의해 O \(log n\)|빠른 O \(log n\)|빠른 O \(log n\)|아니요|  
|Multimap 빨강\-검정|예 \(키로\)|키 O\(log n\) \(키 마다 여러 값\)|빠른 O \(log n\)|빠른 O \(log n\)|예 \(키 마다 여러 값\)|  
  
## CTraits 개체 사용  
 ATL 컬렉션 클래스를 사용 하 여 광범위 한 사용자 정의 데이터 형식 저장할 수 있습니다 대로 비교 등 중요 한 기능을 무시할 수 유용 합니다.  CTraits 클래스를 사용 하 여 얻을 수 있습니다.  
  
 CTraits 클래스, 비슷하지만 MFC 컬렉션 클래스의 도우미 함수 보다 융통성 있게 됩니다. 참조 [컬렉션 클래스 도우미](../mfc/reference/collection-class-helpers.md) 에 대 한 자세한 내용은.  
  
 컬렉션 클래스를 구성할 때 CTraits 클래스를 지정할 수가 있습니다.  이 클래스는 컬렉션 클래스를 구성 하는 다른 메서드를 호출할 때 비교 등의 작업을 수행 하는 코드가 포함 됩니다.  예를 들어, 자신의 사용자 정의 구조체 목록 개체가 포함 하는 경우에 특정 멤버 변수만 비교 하려면 같음 테스트를 재정의할 좋습니다.  이 방식으로 목록 개체의 Find 메서드가 더 유용 하 게 작동 합니다.  
  
## 예제  
  
### 코드  
 [!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/CPP/atl-collection-classes_1.cpp)]  
  
## 설명  
 CTraits 클래스 목록을 참조 하십시오.  [컬렉션 클래스](../atl/collection-classes.md).  
  
 다음 다이어그램은 CTraits 클래스의 클래스 계층 구조를 보여 줍니다.  
  
 ![컬렉션 클래스 특성 계층 구조](../atl/media/vctraitscollectionclasseshierarchy.png "vcTraitsCollectionClassesHierarchy")  
  
## 컬렉션 클래스 샘플  
 다음 샘플 컬렉션 클래스를 보여 줍니다.  
  
-   [MMXSwarm 샘플](../top/visual-cpp-samples.md)  
  
-   [DynamicConsumer 샘플](../top/visual-cpp-samples.md)  
  
-   [UpdatePV 샘플](../top/visual-cpp-samples.md)  
  
-   [Marquee 샘플](../top/visual-cpp-samples.md)  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [컬렉션 클래스](../atl/collection-classes.md)