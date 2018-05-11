---
title: CArchive 개체를 만드는 두 가지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87abaa5a3564c61a6944e0cc31e81375f92a3a80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive 개체를 만드는 두 가지 방법
두 가지 방법으로 만들 수는 `CArchive` 개체:  
  
-   [CArchive 개체는 프레임 워크를 통해 암시적 생성](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [CArchive 개체의 명시적 만들기](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> CArchive 개체는 프레임 워크를 통해 암시적 생성  
 가장 일반적이 고, 쉬운 방법은 만드는 프레임 워크는 `CArchive` 저장, 다른 이름으로 저장 및 열기 명령을 파일 메뉴에서 사용 하는 대신에 대 한 개체입니다.  
  
 프레임 워크 이름으로 저장 명령을 파일 메뉴에서를 발급 하는 사용자 응용 프로그램의 경우는 다음과 같습니다.  
  
1.  표시는 **다른 이름으로 저장** 대화 상자는 사용자 로부터 파일 이름을 가져옵니다.  
  
2.  사용자에으로 라는 파일을 열어서는 `CFile` 개체입니다.  
  
3.  만듭니다는 `CArchive` 이 가리키는 개체를 `CFile` 개체입니다. 만드는 `CArchive` 개체, 프레임 워크 "store" 모드를 설정 (작성, 직렬화) "load" 달리 (읽기, 역직렬화) 합니다.  
  
4.  호출의 `Serialize` 함수에 정의 된 프로그램 **CDocument**-에 대 한 참조를 전달 하는 클래스를 파생는 `CArchive` 개체입니다.  
  
 문서의 `Serialize` 함수에는 다음 데이터를 쓰는 `CArchive` 곧에 설명 된 대로 개체입니다. 반환 될 때 프로그램 `Serialize` 함수, 프레임 워크 제거는 `CArchive` 개체 차례로 `CFile` 개체입니다.  
  
 따라서 만드는 프레임 워크를 사용 하는 경우는 `CArchive` 문서의 구현가 해야 할 모든 개체, 문서에 대 한 `Serialize` 기록 하는 보관 파일에서 읽고 함수입니다. 도 구현 해야 할 `Serialize` 에 대 한 `CObject`-파생 개체를 문서의 `Serialize` 함수를 직접 또는 간접적으로 차례로 serialize 합니다.  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive 개체의 명시적 만들기  
 프레임 워크를 통해 문서를 직렬화 하는 작업 외에도 기타 경우 필요할 때에 대해서는 `CArchive` 개체입니다. 가 나타내는 클립보드의 데이터를 serialize 하려는 하는 예를 들어 한 `CSharedFile` 개체입니다. 또는 프레임 워크에서 제공한 것과에서 다른 파일을 저장 하기 위한 사용자 인터페이스를 사용 하는 것이 좋습니다. 이 경우 명시적으로 만들어야는 `CArchive` 개체입니다. 이렇게 하면 프레임 워크는 동일한 방식으로 다음 절차를 사용 합니다.  
  
#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive 개체를 명시적으로  
  
1.  생성 된 `CFile` 개체 또는 개체에서 파생 된 `CFile`합니다.  
  
2.  전달 된 `CFile` 개체에 대 한 생성자를 `CArchive`다음 예제에 나온 것 처럼:  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     두 번째 인수는 `CArchive` 생성자는 저장 하거나 데이터를 로드 하는 파일에 대 한 보관 파일을 사용 하는지 여부를 지정 하는 열거형된 값입니다. `Serialize` 호출 하 여이 상태를 확인 하는 개체의 함수는 `IsStoring` 보관 개체에 대 한 함수입니다.  
  
 마쳤으면 저장 하거나 데이터를 로드 하는 `CArchive` 개체를 닫습니다. 하지만 `CArchive` (및 `CFile`) 개체는 자동으로 닫고 보관 파일 (파일), 것이 좋습니다 있으므로 명시적으로 오류에서 복구를 보다 쉽게 수 있기 때문입니다. 오류 처리에 대 한 자세한 내용은 문서 참조 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
#### <a name="to-close-the-carchive-object"></a>CArchive 개체  
  
1.  다음 예에서는를 닫으려면는 `CArchive` 개체:  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)

