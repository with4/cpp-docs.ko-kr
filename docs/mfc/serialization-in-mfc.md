---
title: "MFC의 serialization | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c648e32865f73bda5f896f26c495184f964c41d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-in-mfc"></a>MFC의 Serialization
이 문서에서는 프로그램의 모든 실행에 MFC Microsoft Foundation Class 라이브러리 () 개체 간에 유지를 제공 하는 serialization 메커니즘을 설명 합니다.  
  
 Serialization은 프로세스 쓰거나 읽는 개체 또는 디스크 파일을 같은 영구 저장 매체에서입니다. 직렬화 하는 동안 또는 프로그램으로 실행 된 후에 구조적된 데이터 (예: c + + 클래스 또는 구조체)의 상태를 유지 하기 위해 필요한 상황에 이상적입니다. MFC에서 제공 된 serialization 개체를 사용 하 여 사용자 파일 작업을 수동으로 수행 해야에서 하므로 표준 되 고 일관 된 방식으로 사용할 수 있습니다.  
  
 MFC 클래스의 serialization에 대 한 기본 제공 지원을 제공 `CObject`합니다. 모든 클래스에서 파생 되는 따라서 `CObject` 활용할 수 `CObject`의 serialization 프로토콜입니다.  
  
 Serialization의 기본 개념은 개체 일반적으로 영구적 저장소로 해당 멤버 변수의 값으로 표시 되는 현재 상태에 쓸 수 있어야 합니다. 나중, 읽거나 저장소에서 개체의 상태를 역직렬화 하 여 개체를 다시 만들 수 있습니다. 직렬화 개체 포인터와 개체를 serialize 할 때 사용 되는 개체에 대 한 순환 참조의 모든 세부 사항을 처리 합니다. 핵심 개체 자체가 읽기 및 쓰기 자체의 상태에 대 한 책임 지는 것입니다. 따라서를 클래스에 대 한 기본 직렬화 작업 구현 해야 합니다. 아티클 Serialization 그룹에서와 같이 클래스에이 기능을 추가 쉽습니다.  
  
 MFC의 개체를 사용 하 여는 `CArchive` 저장 매체와 serialize 할 개체 간의 중개자는 클래스입니다. 이 개체는 항상 연관는 `CFile` 읽기 또는 쓰기 요청 된 작업 인지 및 파일 이름을 포함 하 여 serialization에 필요한 정보를 얻을 수 있는 개체입니다. Serialization 작업을 수행 하는 개체를 사용할 수는 `CArchive` 저장소 미디어의 특성에 관계 없이 개체입니다.  
  
 A `CArchive` 오버 로드 된 삽입을 사용 하 여 개체 (**<\<**) 및 추출 (**>>**) 쓰기 및 읽기 작업을 수행 하는 연산자입니다. 자세한 내용은 참조 [를 저장 하 고 보관을 통해 Cobject 로드](../mfc/storing-and-loading-cobjects-via-an-archive.md) 문서의 Serialization: 개체를 직렬화 합니다.  
  
> [!NOTE]
>  혼동 하지 마십시오는 `CArchive` 서식 있는 텍스트를만 범용 iostream 클래스에는 클래스입니다. `CArchive` 클래스는 이진 형식의 serialize 된 개체에 대 한 합니다.  
  
 원할 경우에 영구 데이터 저장소에 대 한 메커니즘을 직접 만들려고 MFC serialization을 무시할 수 있습니다. 사용자의 명령에 대 한 직렬화를 시작 하는 클래스 멤버 함수를 재정의 해야 합니다. 참조 [Technical Note 22](../mfc/tn022-standard-commands-implementation.md) 의 `ID_FILE_OPEN`, **ID_FILE_SAVE**, 및 **ID_FILE_SAVE_AS** 표준 명령입니다.  
  
 다음 문서는 직렬화에 필요한 두 가지 기본 작업을 설명 합니다.  
  
-   [Serialization: Serialize 가능한 클래스 만들기](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)  
  
 문서 [Serialization: Serialization vs. 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md) 경우 직렬화는 데이터베이스 응용 프로그램의 적절 한 입/출력 기술에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [CArchive 클래스](../mfc/reference/carchive-class.md)   
 [CObject 클래스](../mfc/reference/cobject-class.md)   
 [CDocument 클래스](../mfc/reference/cdocument-class.md)   
 [CFile 클래스](../mfc/reference/cfile-class.md)
