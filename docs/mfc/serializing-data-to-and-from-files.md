---
title: "파일로 / 파일에서 데이터를 직렬화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d28b12e19b302f5576d2cd76c931e0036c208185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="serializing-data-to-and-from-files"></a>파일로/파일에서 데이터 Serialize
지 속성의 기본 개념은 개체 영구적 저장소로 해당 멤버 변수의 값으로 표시 되는 현재 상태에 쓸 수 있어야 합니다. 나중에, 개체는 읽거나 "," 개체의 상태 역직렬화 영구 저장소에서 다시 만들 수 있습니다. 여기서 중요 한 점은 개체 자체가 읽기 및 쓰기 자체의 상태에 대 한 책임 된다는 점입니다. 따라서 영구 되려면 클래스에 대 한 기본 직렬화 작업 구현 해야 합니다.  
  
 프레임 워크에 대 한 응답으로 저장 디스크 파일에 문서를 저장 하기 위한 기본 구현을 제공 하 고 파일 메뉴와 디스크 파일 열기 명령에 대 한 응답에서에서 문서를 로드 하는 것에 대 한 이름으로 저장 명령입니다. 매우 적은 노력 하 고 파일에서 해당 데이터를 읽고 쓰는 데는 문서의 기능을 구현할 수 있습니다. 해야 할 것이 중요 재정의가 [Serialize](../mfc/reference/cobject-class.md#serialize) 문서 클래스에 멤버 함수입니다.  
  
 MFC 응용 프로그램 마법사의 재정의 기본 배치는 **CDocument** 멤버 함수 `Serialize` 문서 클래스를 만듭니다. 응용 프로그램의 멤버 변수를 구현한 후에 입력할 수 있습니다 프로그램 `Serialize` "보관 개체" 파일에 연결 된 데이터를 전송 하는 코드를 재정의 합니다. A [CArchive](../mfc/reference/carchive-class.md) 개체는 비슷합니다는 `cin` 및 `cout` c + + iostream 라이브러리의 개체를 입/출력 합니다. 그러나 `CArchive` 이진 형식으로 서식 있는 텍스트를 읽고 씁니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [serialization](../mfc/serialization-in-mfc.md)  
  
-   [Serialization에 대 한 문서의 역할](#_core_the_document.92.s_role_in_serialization)  
  
-   [Serialization에 대 한 데이터의 역할](#_core_the_data.92.s_role_in_serialization)  
  
-   [Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)  
  
##  <a name="_core_the_document.92.s_role_in_serialization"></a>Serialization에 대 한 문서의 역할  
 저장 하 고 문서를 호출 하 여 명령으로 저장할 프레임 워크의 파일 메뉴 열기를 자동으로 응답 `Serialize` 구현 된 경우 멤버 함수입니다. `ID_FILE_OPEN` 명령, 예를 들어 응용 프로그램 개체에서 처리기 함수를 호출 합니다. 이 과정에서 사용자에 게 표시 하 고 파일 열기 대화 상자에 응답 하 고 프레임 워크는 사용자가 파일 이름을 가져옵니다. 프레임 워크 만듭니다는 `CArchive` 개체에 대해 설정한 문서에 데이터를 로드 하 고 전달 된 보관 `Serialize`합니다. 프레임 워크에 이미 파일을 열었습니다. 코드에서 문서의 `Serialize` 멤버 함수는 필요에 따라 데이터 개체를 다시 생성할 아카이브를 통해 데이터를 읽고 있습니다. Serialization에 대 한 자세한 내용은 문서 참조 [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
##  <a name="_core_the_data.92.s_role_in_serialization"></a>Serialization에 대 한 데이터의 역할  
 일반적으로 클래스 형식의 데이터는 자신을 serialize 할 수 있어야 합니다. 즉, 보관 파일에 있는 개체를 전달 하면 개체 자체 보관 파일에 작성 하는 방법 및 보관 파일에서 읽는 하는 방법을 알고 있어야 합니다. MFC는 클래스를 이러한 방식으로 직렬화 하기 위한 지원을 제공 합니다. 데이터 형식을 정의 하는 클래스를 디자인 하 고 해당 유형의 데이터를 serialize 하려는 경우에 serialization에 대 한 설계 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 사용](../mfc/using-documents.md)

