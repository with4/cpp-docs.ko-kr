---
title: '방법: 형식이 안전한 컬렉션 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcd1fbce9e6dda649da8fe2e53fc7dc70db1da33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-a-type-safe-collection"></a>방법: 형식이 안전한 컬렉션 만들기
이 문서에서는 사용자 지정 데이터 형식에 대 한 형식이 안전한 컬렉션을 확인 하는 방법을 설명 합니다. 다음과 같은 내용을 다룹니다.  
  
-   [형식 안전성에 대 한 템플릿 기반 클래스를 사용 하 여](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [도우미 함수 구현](#_core_implementing_helper_functions)  
  
-   [비템플릿 컬렉션 클래스를 사용 하 여](#_core_using_nontemplate_collection_classes)  
  
 Microsoft Foundation Class 라이브러리는 c + + 템플릿을 기반으로 하는 미리 정의 된 형식이 안전한 컬렉션을 제공 합니다. 템플릿 되기 때문에 이러한 클래스를의 형식 캐스팅 및 비템플릿 클래스를 사용 하 여이 용도 대 한 기타 추가 작업 없이 사용 편이성과 형식 안전성을 제공 합니다. MFC 샘플 [수집](../visual-cpp-samples.md) MFC 응용 프로그램에서 템플릿 기반 컬렉션 클래스의 사용을 보여 줍니다. 일반적으로 새 컬렉션 코드를 작성 하는 언제 든 지 이러한 클래스를 사용 합니다.  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> 형식 안전성에 대 한 템플릿 기반 클래스를 사용 하 여  
  
#### <a name="to-use-template-based-classes"></a>템플릿 기반 클래스를 사용 하려면  
  
1.  컬렉션 클래스 형식의 변수를 선언 합니다. 예를 들어:  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  컬렉션 개체의 함수는 멤버를 호출 합니다. 예를 들어:  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  필요한 경우 구현에서 [도우미 함수](../mfc/reference/collection-class-helpers.md) 및 [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements)합니다. 이러한 함수를 구현 하는 정보를 참조 하십시오. [도우미 함수 구현](#_core_implementing_helper_functions)합니다.  
  
 이 예제에는 정수 목록이의 선언을 보여 줍니다. 1 단계에서 첫 번째 매개 변수는 목록의 요소로 저장 된 데이터의 형식입니다. 두 번째 매개 변수 데이터를 전달 하 고와 같은 컬렉션 클래스의 멤버 함수에서 반환 하는 방법을 지정 **추가** 및 `GetAt`합니다.  
  
##  <a name="_core_implementing_helper_functions"></a> 도우미 함수 구현  
 템플릿 기반 컬렉션 클래스 `CArray`, `CList`, 및 `CMap` 파생 된 컬렉션 클래스에 대 한 필요에 따라 사용자 지정할 수 있는 5 개의 글로벌 도우미 함수를 사용 합니다. 이러한 도우미 함수에 대 한 자세한 내용은 참조 [컬렉션 클래스 도우미](../mfc/reference/collection-class-helpers.md) 에 *MFC 참조*합니다. Serialization 함수는 템플릿 기반 컬렉션 클래스의 대부분의 사용자에 필요.  
  
###  <a name="_core_serializing_elements"></a> 요소를 직렬화 하는 작업  
 `CArray`, `CList`, 및 `CMap` 호출 클래스 `SerializeElements` 컬렉션 요소를 저장 하거나 보관에서 읽어 주시기 합니다.  
  
 기본 구현에서 `SerializeElements` 도우미 함수가 수행 하는 비트 쓰기 개체 중에서 보관 저장소에 또는 비트 개체에 저장 되 고 있는지 여부에 따라 개체에 대 한 보관 파일에서 읽기 또는 보관 파일에서 검색 합니다. 재정의 `SerializeElements` 이 작업에 적합 하지 않은 경우.  
  
 컬렉션에서 파생 된 개체를 저장 하는 경우 `CObject` 사용 하는 `IMPLEMENT_SERIAL` 컬렉션 요소 클래스의 구현에서 매크로 들에 기본 제공 되는 serialization 기능 `CArchive` 및 `CObject`:  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]  
  
 에 대 한 오버 로드 된 삽입 연산자 `CArchive` 호출 `CObject::Serialize` (또는 해당 함수에 대 한 재정의) 각각에 대해 **CPerson** 개체입니다.  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> 비템플릿 컬렉션 클래스를 사용 하 여  
 MFC는 또한 MFC 버전 1.0에 도입 된 컬렉션 클래스를 지원 합니다. 이러한 클래스는 템플릿을 기반으로 하지 합니다. 지원 되는 형식의 데이터를 포함 하는 데 사용 될 수 `CObject*`, **UINT**, `DWORD`, 및 `CString`합니다. 이러한 미리 정의 된 컬렉션을 사용할 수 있습니다 (예: `CObList`)에서 파생 된 모든 개체의 컬렉션을 보유 하 `CObject`합니다. MFC와 같은 기본 형식을 보유 하는 다른 미리 정의 된 컬렉션을 제공 **UINT** 포인터를 무효화 하 고 (`void`*). 그러나 일반적으로 유용 보다 구체적인 클래스와 해당 파생 클래스의 개체를 보유 하는 사용자 지정 형식이 안전한 컬렉션을 정의할 수 있습니다. 하지 컬렉션 클래스와 함께 이렇게 템플릿을 기반으로 하는 템플릿 기반 클래스를 사용 하 여 보다 더 많은 작업 합니다.  
  
 두 가지 방법으로 비템플릿 컬렉션을 사용 하 여 형식이 안전한 컬렉션을 만들려면:  
  
1.  비템플릿 컬렉션 유형 캐스팅 필요한 경우 사용 합니다. 이 방법이 더 쉽습니다.  
  
2.  파생 하 고 비템플릿 형식이 안전한 컬렉션을 확장 합니다.  
  
#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>형식 캐스팅을 사용한 비템플릿 컬렉션 사용 기준  
  
1.  와 같은 비템플릿 클래스 중 하나를 사용 `CWordArray`, 직접 합니다.  
  
     예를 들어 만들 수 있습니다는 `CWordArray` 하 고, 32 비트 값을 추가한 다음 검색 합니다. 작업을 수행 하는 더 많은 일은 없습니다. 미리 정의 된 기능을 사용할 것입니다.  
  
     사용할 수도 있습니다를 미리 정의 된 컬렉션에 같은 `CObList`에서 파생 된 모든 개체를 보관할 수 `CObject`합니다. A `CObList` 컬렉션에 대 한 포인터를 보유 하기 위해 정의 `CObject`합니다. 이후 적절 한 형식으로 결과 캐스팅 해야 목록에서 개체를 검색 하는 경우는 `CObList` 함수에 대 한 포인터를 반환 합니다. `CObject`합니다. 예를 들어, 저장 하는 경우 `CPerson` 개체에 `CObList` 검색 된 요소 수에 대 한 포인터를 캐스팅 해야 하는 컬렉션을 `CPerson` 개체입니다. 다음 예제에서는 한 `CObList` 를 보관할 컬렉션 `CPerson` 개체:  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]  
  
     미리 정의 된 컬렉션 형식을 사용 하 고 필요에 따라 캐스팅이 기술은 다양 한 컬렉션 요구 사항에 대 한 적절 한 수 있습니다. 추가 기능이 나 더 많은 형식 안전성을 해야 하는 경우 템플릿 기반 클래스를 사용 하거나 다음 절차를 수행 합니다.  
  
#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>파생 시켜 비템플릿 형식이 안전한 컬렉션을 확장 하려면  
  
1.  미리 정의 된 비템플릿 클래스 중 하나에서 사용자 고유의 컬렉션 클래스를 파생 시킵니다.  
  
     클래스를 파생 하는 경우에 기존 함수에 형식이 안전한 인터페이스를 제공 하는 형식이 안전한 래퍼 함수를 추가할 수 있습니다.  
  
     예를 들어, 목록에서 파생 된 경우 `CObList` 보유할 `CPerson` 개체 래퍼 함수를 추가할 수 있습니다 `AddHeadPerson` 및 `GetHeadPerson`아래와 같이, 합니다.  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]  
  
     이러한 래퍼 함수를 추가 하 고 검색 하는 형식이 안전한 방법을 제공 `CPerson` 파생된 목록의 개체입니다. 에 대 한을 확인할 수 있습니다는 `GetHeadPerson` 함수를 형식 캐스팅을 캡슐화 하 고 있는 하기만 합니다.  
  
     기존 기능 형식이 안전한 래퍼에서 래핑하는 대신 컬렉션의 기능을 확장 하는 새 함수를 정의 하 여 새 기능을 추가할 수도 있습니다. 예를 들어 문서 [CObject 컬렉션의 모든 개체 삭제](../mfc/deleting-all-objects-in-a-cobject-collection.md) 목록에 포함 된 모든 개체를 삭제 하는 함수에 설명 합니다. 이 함수는 멤버 함수로 파생된 클래스에 추가할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션](../mfc/collections.md)

