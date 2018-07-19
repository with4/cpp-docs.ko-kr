---
title: CObject 컬렉션의 모든 개체 삭제 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f57e503e43bdb637b85e4642349203b9f2e8aa6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348825"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject 컬렉션의 모든 개체 삭제
이 문서에서는 (하지 않고 컬렉션 개체 자체를 삭제)는 컬렉션의 모든 개체를 삭제 하는 방법에 설명 합니다.  
  
 컬렉션의 모든 개체를 삭제 하려면 `CObject`s (또는에서 파생 된 개체의 `CObject`), 문서에 설명 된 반복 기술 중 하나를 사용 [컬렉션의 모든 멤버에 액세스](../mfc/accessing-all-members-of-a-collection.md) 에 있는 각 개체를 삭제 하려면 설정 합니다.  
  
> [!CAUTION]
>  컬렉션의 개체를 공유할 수 있습니다. 즉, 컬렉션 개체에 대 한 포인터를 유지 하지만 프로그램의 다른 부분에서 동일한 개체에 대 한 포인터도 있습니다. 개체를 사용 하 여 모든 부분이 완료 될 때까지 공유 하는 개체를 삭제 하지 않도록 주의 해야 합니다.  
  
 이 문서에서 개체를 삭제 하는 방법을 보여 줍니다.  
  
-   [목록](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [배열](#_core_to_delete_all_elements_in_an_array)  
  
-   [지도](#_core_to_delete_all_elements_in_a_map)  
  
#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>  CObject에 대 한 포인터 목록에서 모든 개체를 삭제 하려면  
  
1.  사용 하 여 `GetHeadPosition` 및 `GetNext` 목록에서 반복 하 합니다.  
  
2.  사용 하 여는 **삭제** 반복에서 발생 하는 대로 각 개체를 삭제 하는 연산자입니다.  
  
3.  호출 된 `RemoveAll` 요소와 관련 된 개체를 삭제 한 후 목록에서 모든 요소를 제거 하는 함수입니다.  
  
 목록에서 모든 개체를 삭제 하는 방법을 보여 주는 다음 예제 `CPerson` 개체입니다. 목록에서 각 개체에 대 한 포인터는 한 `CPerson` 원래 힙에 할당 된 개체입니다.  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 마지막 함수 호출 `RemoveAll`, 목록에서 모든 요소를 제거 하는 목록 멤버 함수입니다. 멤버 함수 `RemoveAt` 단일 요소를 제거 합니다.  
  
 요소의 개체를 삭제 하 고 요소 자체를 제거 간 차이 확인 합니다. 목록에서 요소를 단순히 제거에 목록 개체에 대 한 참조를 제거 합니다. 개체가는 메모리에 계속 있습니다. 개체를 삭제 하면 더 이상 존재 하 고 메모리가 회수 됩니다. 즉, 목록을 더 이상 존재 하는 개체에 액세스 하려고 시도 하지 않도록 요소의 개체가 삭제 된 후에 즉시 요소를 제거 하는 것이 중요 합니다.  
  
#### <a name="_core_to_delete_all_elements_in_an_array"></a>  배열의 모든 요소를 삭제 하려면  
  
1.  사용 하 여 `GetSize` 과 배열을 통해 반복 하는 정수 인덱스 값입니다.  
  
2.  사용 하 여는 **삭제** 반복에서 발생 하는 대로 각 요소를 삭제 하는 연산자입니다.  
  
3.  호출 된 `RemoveAll` 함수를 삭제 한 후에 배열에서 모든 요소를 제거 합니다.  
  
     배열의 모든 요소를 삭제 하기 위한 코드는 다음과 같습니다.  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 호출할 수 목록 위의 예에서와 같이 `RemoveAll` 배열의 모든 요소를 제거 하려면 또는 `RemoveAt` 개별 요소를 제거 하려면.  
  
#### <a name="_core_to_delete_all_elements_in_a_map"></a> Map의 모든 요소를 삭제 하려면  
  
1.  사용 하 여 `GetStartPosition` 및 `GetNextAssoc` 배열을 통해 반복 하 합니다.  
  
2.  사용 하 여는 **삭제** 반복에서 발생 하는 대로 키 및/또는 각 지도 요소에 대 한 값을 삭제 하는 연산자입니다.  
  
3.  호출 된 `RemoveAll` 함수를 삭제 한 후 맵에서 모든 요소를 제거 합니다.  
  
     모든 요소를 삭제 하기 위한 코드는 `CMap` 컬렉션은 다음과 같습니다. Map의 각 요소에 키로 문자열 및 `CPerson` 개체 (에서 파생 된 `CObject`) 값으로.  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 호출할 수 있습니다 `RemoveAll` 맵에서 모든 요소를 제거 하려면 또는 `RemoveKey` 지정된 된 키와 개별 요소를 제거 하려면.  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션의 모든 멤버에 액세스](../mfc/accessing-all-members-of-a-collection.md)

