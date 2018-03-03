---
title: "방법: 템플릿 클래스에 대 한 메시지 맵 만들기 | Microsoft Docs"
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
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e593d1b75265a1c58c82278920bda92ddf58929
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>방법: 템플릿 클래스에 대한 메시지 맵 만들기
메시지 매핑 MFC의 Windows 메시지를 적절 한 c + + 개체 인스턴스 수 있는 효율적인 방법을 제공 합니다. MFC 메시지 맵에 대상의 예로 응용 프로그램 클래스, 문서 및 뷰 클래스, 컨트롤 클래스 및 등이 있습니다.  
  
 기존 MFC 메시지 맵을 사용 하 여 선언 되는 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 메시지 맵 각 메시지-처리기 클래스 메서드에 대해 매크로 항목의 시작 부분을 선언 하는 매크로 및 마지막으로 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)메시지 맵에의 끝을 선언 하는 매크로입니다.  
  
 제한 사항은 일반 하나는 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 매크로 템플릿 인수를 포함 하는 클래스와 함께에서 사용할 경우에 발생 합니다. 템플릿 클래스를 사용할 때이 매크로 매크로 확장 중 누락 된 템플릿 매개 변수 때문에 컴파일 타임 오류를 발생 합니다. [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) 매크로 매핑합니다 메시지를 직접 선언에 대 한 단일 템플릿 인수를 포함 하는 클래스를 허용 하도록 설계 되었습니다.  
  
## <a name="example"></a>예  
 예를 살펴보겠습니다 있는 MFC [CListBox](../mfc/reference/clistbox-class.md) 클래스 외부 데이터 원본 사용 하 여 동기화를 제공 하도록 확장 됩니다. 가상의 **CSyncListBox** 클래스는 다음과 같이 선언 됩니다.  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 **CSyncListBox** 클래스는 템플릿 기반와 동기화 할 데이터 원본을 설명 하는 단일 형식. 클래스의 메시지 맵을 참여 하는 세 가지 방법을 선언: **OnPaint**, **OnDestroy**, 및 **OnSynchronize**합니다. **OnSynchronize** 메서드는 다음과 같이 구현 됩니다.  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 위의 구현 하면는 **CSyncListBox** 구현 하는 클래스 형식에 특수화 된 것으로 클래스는 **GetCount** 메서드를 같은 **CArray**, **CList**, 및 **CMap**합니다. **StringizeElement** 함수는 프로토타입화는 다음에는 템플릿 함수.  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 일반적으로이 클래스에 대 한 메시지 맵은로 정의 됩니다.  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 여기서 **LBN_SYNCHRONIZE** 같은 응용 프로그램에 의해 정의 된 사용자 지정 메시지입니다.  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 위의 매크로 맵 컴파일되지 않고 때문을 템플릿 지정에 대 한는 **CSyncListBox** 매크로 확장 중에 클래스 누락 됩니다. **BEGIN_TEMPLATE_MESSAGE_MAP** 매크로 확장된 매크로 맵에 지정 된 템플릿 매개 변수를 통합 하 여 해결 되었습니다. 이 클래스에 대 한 메시지 맵을 다음과 같이 됩니다.  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 다음의 샘플 사용을 보여 줍니다.는 **CSyncListBox** 클래스 사용을 **CStringList** 개체:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 테스트를 완료 하는 **StringizeElement** 작업할 함수를 특수화할 수 해야는 **CStringList** 클래스:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)   
 [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)

