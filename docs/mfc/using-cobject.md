---
title: CObject 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0fab92dddc10a66fe350d343f1fd280ce5c9a50
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027153"
---
# <a name="using-cobject"></a>CObject 사용
[CObject](../mfc/reference/cobject-class.md) 대부분 Microsoft Foundation 클래스 라이브러리 (MFC)의 루트 기본 클래스입니다. `CObject` 클래스 serialization 지 원하는, 런타임 클래스 정보 및 개체 진단 출력을 포함 하 여 사용자 고유의 프로그램 개체를 통합할 수 있는 많은 유용한 기능을 포함 합니다. 클래스를 파생 하는 경우 `CObject`, 이러한 클래스를 이용할 수 있습니다 `CObject` 기능입니다.  
  
## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요  
  
-   [CObject에서 클래스를 파생 시킵니다.](../mfc/deriving-a-class-from-cobject.md)  
  
-   [파생된 클래스 내에 런타임 클래스 정보, 동적 생성 및 serialization에 대 한 지원 추가](../mfc/specifying-levels-of-functionality.md)  
  
-   [런타임 클래스 정보 액세스](../mfc/accessing-run-time-class-information.md)  
  
-   [개체를 동적으로 만들기](../mfc/dynamic-object-creation.md)  
  
-   [진단 목적을 위해 개체의 데이터를 덤프](http://msdn.microsoft.com/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   개체의 내부 상태 유효성 검사 (참조 [MFC ASSERT_VALID 및 CObject::AssertValid](http://msdn.microsoft.com/7654fb75-9e9a-499a-8165-0a96faf2d5e6))  
  
-   [영구적 저장소로 직렬화 하는 자체 클래스](../mfc/serialization-in-mfc.md)  
  
-   목록을 보려면 [Frequently Asked Questions CObject](../mfc/cobject-class-frequently-asked-questions.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [CRuntimeClass 구조체](../mfc/reference/cruntimeclass-structure.md)   
 [파일](../mfc/files-in-mfc.md)   
 [serialization](../mfc/serialization-in-mfc.md)

