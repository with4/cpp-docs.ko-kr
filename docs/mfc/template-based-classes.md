---
title: "템플릿 기반 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2beb417bdedab6196ff6d27a387c4b61f083c4ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="template-based-classes"></a>템플릿 기반 클래스
이 문서에서는 MFC 3.0 이상 버전의에서 형식이 안전한 템플릿 기반 컬렉션 클래스에 설명 합니다. 이러한 서식 파일을 사용 하 여 형식이 안전한 컬렉션을 만드는 것이 더 편리 하 고 사용 하면 형식 안전성을 템플릿 기반 컬렉션 클래스를 사용 하 여 보다 효과적으로 제공 합니다.  
  
 MFC는 두 가지 범주의 템플릿 기반 컬렉션을 미리 정의 합니다.  
  
-   [단순 배열, 목록 및 맵 클래스](#_core_using_simple_array.2c_.list.2c_.and_map_templates)  
  
     `CArray`, `CList`, `CMap`  
  
-   [배열, 목록 및 형식화 된 포인터의 맵을](#_core_using_typed.2d.pointer_collection_templates)  
  
     `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`  
  
 간단한 컬렉션 클래스는 모든 클래스에서 파생 된 `CObject`, 직렬화, 동적 생성 및 기타 속성을 상속 하도록 `CObject`합니다. 형식화 된 포인터 컬렉션 클래스에서 파생 되는 클래스를 지정 하도록 요구-같은 MFC에 미리 정의 된 비템플릿 포인터 컬렉션 중 하나인 `CPtrList` 또는 `CPtrArray`합니다. 지정된 된 기본 클래스에서 상속 되는 새로운 컬렉션 클래스 및 형식 안전성을 적용 하는 기본 클래스 멤버에 캡슐화 된 호출을 사용 하는 새 클래스의 멤버 함수입니다.  
  
 C + + 템플릿에 대 한 자세한 내용은 참조 하십시오. [템플릿](../cpp/templates-cpp.md) 에 *c + + 언어 참조*합니다.  
  
##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>단순 배열, 목록 및 맵 템플릿을 사용 하 여  
 간단한 컬렉션 서식 파일을 사용 하려면 이러한 컬렉션에 저장할 수 있는 데이터의 어떤 종류와 컬렉션 선언에서 사용 하도록 매개 변수를 알고 있어야 합니다.  
  
###  <a name="_core_simple_array_and_list_usage"></a>단순 배열 및 목록 사용  
 단순 배열 및 목록 클래스 [CArray](../mfc/reference/carray-class.md) 및 [CList](../mfc/reference/clist-class.md), 두 개의 매개 변수: *형식* 및 `ARG_TYPE`합니다. 이러한 클래스에서 지정 하는 모든 데이터 형식을 저장할 수는 *형식* 매개 변수:  
  
-   와 같은 기본 c + + 데이터 형식 `int`, `char`, 및 **float**  
  
-   C + + 구조체와 클래스  
  
-   정의 하는 다른 형식  
  
 편 및 효율성을 위해 사용할 수 있습니다는 `ARG_TYPE` 매개 변수를 함수 인수 유형을 지정 합니다. 일반적으로 지정 `ARG_TYPE` 에 명명 된 형식에 대 한 참조로는 *형식* 매개 변수입니다. 예:  
  
 [!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]  
  
 첫 번째 예제에서는 배열 컬렉션을 선언 `myArray`, 포함 된 `int`s입니다. 두 번째 예제에서는 선언 목록 컬렉션 `myList`, 저장 하는 `CPerson` 개체입니다. 지정 된 형식의 인수를 사용 하는 컬렉션 클래스의 특정 멤버 함수는 `ARG_TYPE` 템플릿 매개 변수입니다. 예를 들어는 **추가** 클래스의 멤버 함수 `CArray` 사용는 `ARG_TYPE` 인수:  
  
 [!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]  
  
###  <a name="_core_simple_map_usage"></a>단순 맵 사용  
 단순 맵 클래스 [CMap](../mfc/reference/cmap-class.md), 4 개의 매개 변수: *키*, `ARG_KEY`, *값*, 및 `ARG_VALUE`합니다. 배열 및 목록 클래스와 마찬가지로 맵 클래스에는 모든 데이터 형식을 저장할 수 있습니다. 배열 및 인덱싱하고 저장 하 고 데이터의 순서 있는 목록을 달리 맵은 키와 값: 값의 연결 된 키를 지정 하 여 지도에 저장 된 값에 액세스 합니다. *키* 매개 변수는 맵에 저장 된 데이터에 액세스 하는 데 사용 되는 키의 데이터 형식을 지정 합니다. 경우 유형의 *키* 구조체 또는 클래스는 `ARG_KEY` 매개 변수에서 지정 된 형식에 대 한 참조는 대개 *키*합니다. *값* 매개 변수는 맵에 저장 된 항목의 형식을 지정 합니다. 경우 유형의 `ARG_VALUE` 구조체 또는 클래스는 `ARG_VALUE` 매개 변수에서 지정 된 형식에 대 한 참조는 대개 *값*합니다. 예:  
  
 [!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]  
  
 첫 번째 예제에서는 저장소 `MY_STRUCT` 을 액세스 하 여 두 값이 `int` 키 및 액세스 반환 `MY_STRUCT` 참조로 항목입니다. 두 번째 예제에서는 저장소 `CPerson` 값, 액세스 하 여 `CString` 키를 누른 액세스 한 항목에 대 한 참조를 반환 합니다. 이 예제는 간단한 주소록에서 하면 조회 하는 사람을 성을 기준으로 나타낼 수 있습니다.  
  
 때문에 *키* 매개 변수는 형식 `CString` 및 *KEY_TYPE* 매개 변수는 형식 `LPCSTR`, 키 형식의 항목으로 맵에 저장 되므로 `CString` 있지만 에서도 참조 와 같은 함수가 `SetAt` 형식의 포인터를 통해 `LPCSTR`합니다. 예:  
  
 [!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]  
  
##  <a name="_core_using_typed.2d.pointer_collection_templates"></a>형식화 된 포인터 컬렉션 템플릿 사용  
 형식화 된 포인터 컬렉션 서식 파일을 사용 하려면 이러한 컬렉션에 저장할 수 어떤 종류의 데이터와 컬렉션 선언에서 사용 하도록 매개 변수를 알고 있어야 합니다.  
  
###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a>형식화 된 포인터 배열 및 목록 사용  
 형식화 된 포인터 배열 및 목록 클래스 [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) 및 [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), 두 개의 매개 변수: `BASE_CLASS` 및 *형식*합니다. 이러한 클래스에서 지정 하는 모든 데이터 형식을 저장할 수는 *형식* 매개 변수입니다. 포인터를 저장 하는 비템플릿 컬렉션 클래스 중 하나에서 파생 되므로 이 기본 클래스에서 지정 `BASE_CLASS`합니다. 배열에 대해 사용 하 여 `CObArray` 또는 `CPtrArray`합니다. 목록에 대 한 사용 하 여 `CObList` 또는 `CPtrList`합니다.  
  
 실제로 기반으로 컬렉션을 선언 하는 경우 예를 들어 `CObList`, 새 클래스 뿐 아니라 해당 기본 클래스의 멤버를 상속 하지만 함수 및 연산자를 캡슐화 하 여 형식 안전성을 제공 하는 데 도움이 되는 다양 한 추가 형식이 안전한 멤버 선언 기본 클래스 멤버에 대 한 호출입니다. 이러한를 캡슐화이 할 필요한 모든 형식 변환이 관리합니다. 예:  
  
 [!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]  
  
 첫 번째 예에서는 형식화 된 포인터 배열을 선언 `myArray`에서 파생 된 `CObArray`합니다. 저장 하 고에 대 한 포인터를 반환 하는 배열 `CPerson` 개체 (여기서 `CPerson` 클래스에서 파생 `CObject`). 호출할 수 있습니다 `CObArray` 멤버 함수 또는 하면 새 형식이 안전한을 호출할 수 `GetAt` 및 `ElementAt` 함수 또는 형식이 안전한을 사용 하 여 **** 연산자입니다.  
  
 두 번째 예에서는 형식화 된 포인터 목록 선언 `myList`에서 파생 된 `CPtrList`합니다. 저장 하 고에 대 한 포인터를 반환 하는 목록 `MY_STRUCT` 개체입니다. 클래스에 따라 `CPtrList` 에서 파생 되지 않은 개체에 대 한 포인터를 저장 하는 데 사용 되는 `CObject`합니다. `CTypedPtrList`형식이 안전한 멤버 함수에 개수가: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev`, 및 `GetAt`합니다.  
  
###  <a name="_core_typed.2d.pointer_map_usage"></a>형식화 된 포인터 맵 사용  
 형식화 된 포인터 map 클래스 [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), 세 개의 매개 변수: `BASE_CLASS`, *키*, 및 *값*합니다. `BASE_CLASS` 새 클래스 파생 시키기 위한 클래스를 지정 하는 매개 변수: `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`등입니다. *키* 유사 *키* 에 `CMap`: 조회에 사용 되는 키의 형식을 지정 합니다. *값* 유사 *값* 에 `CMap`: 맵에 저장 된 개체의 형식을 지정 합니다. 예:  
  
 [!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]  
  
 첫 번째 예제에 따라 한 맵이 **CMapPtrToPt**r-사용 하 여 `CString` 에 대 한 포인터에 매핑된 키 `MY_STRUCT`합니다. 형식이 안전한 호출 하 여 저장 된 포인터를 조회할 수 있습니다 `Lookup` 멤버 함수입니다. 사용할 수는 **** 연산자를 저장 된 포인터를 조회 하 고 추가 찾을 수 없는 경우. 형식이 안전한을 사용 하 여 지도 반복할 수 및 `GetNextAssoc` 함수입니다. 또한 함수를 호출할 수 다른 멤버 클래스의 `CMapPtrToPtr`합니다.  
  
 두 번째 예제를 기반으로 한 맵이 **CMapStringToO**b-에 대 한 저장 된 포인터에 매핑된 문자열 키를 사용 하 여 `CMyObject` 개체입니다. 이전 단락에 설명 된 동일한 형식이 안전한 멤버를 사용 하거나 클래스의 멤버를 호출할 수 `CMapStringToOb`합니다.  
  
> [!NOTE]
>  지정 하는 경우는 **클래스** 또는 `struct` 에 대 한 입력은 *값* 매개 변수 보다는 포인터 또는 유형, 클래스 또는 구조체에 대 한 참조는 복사 생성자가 있어야 합니다.  
  
 자세한 내용은 참조 [형식이 안전한 컬렉션을 만드는 방법](../mfc/how-to-make-a-type-safe-collection.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션](../mfc/collections.md)

