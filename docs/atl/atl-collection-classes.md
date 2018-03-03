---
title: "ATL 컬렉션 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- collection classes, choosing
- ConstructElements function
- SerializeElements function
- traits classes
- collection classes, about collection classes
- CTraits classes
- collection classes
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24b0fbdc5ab68319704fb59746862384198f232b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-collection-classes"></a>ATL 컬렉션 클래스
ATL은 데이터 저장 및 액세스에 대 한 많은 클래스를 제공 합니다. 어떤 클래스를 사용 하려는 등의 여러 가지 요인에 따라 달라 집니다.  
  
-   저장할 데이터 양  
  
-   데이터 액세스 성능과 효율성  
  
-   인덱스 또는 키 데이터에 액세스 하는 기능  
  
-   데이터가 정렬 되는 방법  
  
-   개인의 기본 설정  
  
## <a name="small-collection-classes"></a>작은 컬렉션 클래스  
 ATL은 적은 수의 개체를 처리 하기 위한 다음 배열 클래스를 제공 합니다. 그러나 이러한 클래스는 제한 된 고 ATL. 하 여 내부적으로 사용 하도록 설계 프로그램에서 사용 하는 권장 되지 않습니다.  
  
|클래스|데이터 저장소 유형|  
|-----------|--------------------------|  
|[CSimpleArray](../atl/reference/csimplearray-class.md)|적은 수의 개체를 처리 하기 위한 배열 클래스를 구현합니다.|  
|[CSimpleMap](../atl/reference/csimplemap-class.md)|적은 수의 개체를 처리 하기 위한 매핑 클래스를 구현 합니다.|  
  
## <a name="general-purpose-collection-classes"></a>범용 컬렉션 클래스  
 다음 클래스는 배열, 목록 및 맵 구현 그리고 컬렉션 클래스를 범용으로 제공 됩니다.  
  
|클래스|데이터 저장소 유형|  
|-----------|--------------------------|  
|[CAtlArray](../atl/reference/catlarray-class.md)|배열을 구현합니다.|  
|[CAtlList](../atl/reference/catllist-class.md)|목록을 구현합니다.|  
|[CAtlMap](../atl/reference/catlmap-class.md)|그에 따라 키 또는 값으로 데이터를 참조할 수 있습니다는 매핑 구조를 구현 합니다.|  
|[CRBMap](../atl/reference/crbmap-class.md)|빨간색 검정 알고리즘을 사용 하 여 매핑 구조를 구현 합니다.|  
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|빨간색 검정 multimapping 구조를 구현합니다.|  
  
 이러한 클래스는 디버그 빌드에 사용 하면 많은 프로그래밍 오류를 트래핑 됩니다 하지만 성능, 코드를 작성 해야 이러한 검사가 수행 되지 않습니다 정품 빌드에 있습니다.  
  
## <a name="specialized-collection-classes"></a>특수 컬렉션 클래스  
 인터페이스 포인터 및 메모리 포인터를 관리 하기 위한 더 특수 한 컬렉션 클래스도 제공 됩니다.  
  
|클래스|용도|  
|-----------|-------------|  
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|스마트 포인터의 배열을 만들 때 유용한 메서드를 제공 합니다.|  
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|스마트 포인터의 목록을 구성할 때 유용한 메서드를 제공 합니다.|  
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|저장소 `IUnknown` 포인터에 대 한 매개 변수로 사용할 수 있도록 설계 되 고는 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다.|  
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|힙 포인터 목록을 구성할 때 유용한 메서드를 제공 합니다.|  
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|COM 인터페이스 포인터의 배열을 만들 때 유용한 메서드를 제공 합니다.|  
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|COM 인터페이스 포인터의 목록을 구성할 때 유용한 메서드를 제공 합니다.|  
  
## <a name="choosing-a-collection-class"></a>컬렉션 클래스 선택  
 각각의 사용 가능한 컬렉션 클래스는 아래 표에 나와 있는 것 처럼 다양 한 성능 특성을 제공 합니다.  
  
-   열 2와 3에는 액세스 특성 및 각 클래스의 순서를 설명 합니다. 이 표에서 "정렬 여부"는 항목이 삽입되고 삭제되는 순서가 컬렉션의 순서에 따라 결정되는 것을 의미하며 항목이 내용에 따라 정렬된다는 것을 의미하지는 않습니다. "인덱스 여부"는 컬렉션의 항목을 일반 배열의 항목처럼 정수 인덱스로 검색할 수 있음을 의미합니다.  
  
-   각 클래스의 성능 4 및 5 번 열에 설명 합니다. 컬렉션에 항목을 많이 삽입해야 하는 응용 프로그램에서는 삽입 속도가 특히 중요합니다. 다른 응용 프로그램에서는 조회 속도가 더 중요할 수도 있습니다.  
  
-   6번 열에서는 각 모양에 요소가 중복될 수 있는지 여부에 대해 설명합니다.  
  
-   지정 된 컬렉션 클래스 작업의 성능은 작업 컬렉션의 요소 수를 완료 하는 데 필요한 시간 간의 관계를 기준으로 표현 됩니다. 시간 만큼 라인으로 전환 하는 작업 하는 선형적으로 증가 하는 요소 수가 증가할수록은 o (n) 알고리즘으로 설명 됩니다. 이와 반대로 떨어질 수 요소 증가으로 증가 하는 시간의 경과 수행 하는 작업은 O (로그) 알고리즘으로 설명 됩니다. 따라서 성능 면 O (로그) 알고리즘 보다 성능이 뛰어나지만 수 요소 증가와 더 많은 o (n) 알고리즘.  
  
### <a name="collection-shape-features"></a>컬렉션 모양 특징  
  
|모양|Ordered|인덱스|삽입 된<br /><br /> 요소|검색 대상<br /><br /> 지정 된 요소|복제<br /><br /> 요소|  
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|  
|목록|예|아니요|Fast (일정 시간)|느린 o (n)|예|  
|배열|예|Int (일정 시간)으로|경우에 일정 한 시간 끝에 삽입 하는 제외 하 고 느린 o (n)|느린 o (n)|예|  
|맵|아니요|키 (일정 시간)|Fast (일정 시간)|Fast (일정 시간)|아니요(키) 예(값)|  
|빨간색 검정 맵|(키)에 의해 예|O (로그)을 키로|빠른 O (로그)|빠른 O (로그)|아니요|  
|빨간색 검정 Multimap|(키)에 의해 예|키별로 O(log n) (키 당 여러 값)|빠른 O (로그)|빠른 O (로그)|예 (여러 값 키 당)|  
  
## <a name="using-ctraits-objects"></a>CTraits 개체를 사용 하 여  
 다양 한 사용자 정의 데이터 형식 저장 하는 ATL 컬렉션 클래스를 사용할 수 있습니다, 비교 등 중요 한 기능을 무시할 수 유용할 수 있습니다. CTraits 클래스를 사용 하 여 이루어집니다.  
  
 CTraits 클래스와 비슷하기는 하지만 MFC 컬렉션 클래스 도우미 함수; 보다 좀 더 융통적는 참조 [컬렉션 클래스 도우미](../mfc/reference/collection-class-helpers.md) 자세한 정보에 대 한 합니다.  
  
 컬렉션 클래스를 생성할 때는 CTraits 클래스를 지정 옵션이 있습니다. 이 클래스는 컬렉션 클래스를 구성 하는 다른 메서드에 의해 호출 될 경우 비교 등의 작업을 수행 하는 코드를 포함 됩니다. 예를 들어, 사용자 고유의 사용자 정의 구조를 포함 하는 목록 개체를 하는 경우만 특정 멤버 변수를 비교 하려면 같음 테스트를 다시 정의 하는 것이 좋습니다. 이러한 방식으로 목록 개체의 Find 메서드가에 더 유용 하 게 작동 합니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
 [!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]  
  
## <a name="comments"></a>설명  
 목록이 CTraits 클래스에 대 한 참조 [컬렉션 클래스](../atl/collection-classes.md)합니다.  
  
 다음 다이어그램에서는 CTraits 클래스에 대 한 클래스 계층 구조를 보여 줍니다.  
  
 ![컬렉션 클래스에 대 한 특성 계층 구조](../atl/media/vctraitscollectionclasseshierarchy.gif "vctraitscollectionclasseshierarchy")  
  
## <a name="collection-classes-samples"></a>컬렉션 클래스 샘플  
 다음 예제에서는 컬렉션 클래스를 보여 줍니다.  
  
-   [MMXSwarm 샘플](../visual-cpp-samples.md)  
  
-   [DynamicConsumer 샘플](../visual-cpp-samples.md)  
  
-   [UpdatePV 샘플](../visual-cpp-samples.md)  
  
-   [움직이는 텍스트 샘플](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [컬렉션 클래스](../atl/collection-classes.md)

