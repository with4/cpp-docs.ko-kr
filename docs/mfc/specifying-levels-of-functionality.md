---
title: 기능 수준 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f32b9502d2e8bd1c1483d817b759ca204f5c9c1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-levels-of-functionality"></a>기능 수준 지정
이 문서에서는 다음과 같은 수준의 기능을 추가 하는 방법을 설명 프로그램 [CObject](../mfc/reference/cobject-class.md)-파생 클래스:  
  
-   [런타임 클래스 정보](#_core_to_add_run.2d.time_class_information)  
  
-   [동적 만들기 지원](#_core_to_add_dynamic_creation_support)  
  
-   [Serialization 지원](#_core_to_add_serialization_support)  
  
 에 대 한 일반적인 설명은 `CObject` 기능을 문서 참조 [CObject에서 클래스를 파생](../mfc/deriving-a-class-from-cobject.md)합니다.  
  
-   [런타임 클래스 정보](#_core_to_add_run.2d.time_class_information)  
#### <a name="_core_to_add_run.2d.time_class_information"></a> 런타임 클래스 정보를 추가 하려면  
  
1.  클래스를 파생 `CObject`에 설명 된 대로 [CObject에서 클래스를 파생](../mfc/deriving-a-class-from-cobject.md) 문서.  
  
2.  사용 하 여는 `DECLARE_DYNAMIC` 다음과 같이 클래스 선언에서 매크로:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]  
  
3.  사용 하 여는 `IMPLEMENT_DYNAMIC` 매크로 구현 파일에서 (합니다. CPP) 클래스입니다. 이 매크로 인수로 사용 클래스 및 해당 기본 클래스의 이름을 다음과 같습니다.  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  항상 `IMPLEMENT_DYNAMIC` 구현 파일에서 (합니다. CPP) 클래스에 대 한 합니다. `IMPLEMENT_DYNAMIC` 매크로 컴파일하는 동안 한 번만 평가 해야 하 고 따라서 안되며 인터페이스 파일에 (합니다. H)는 둘 이상의 파일에 잠재적으로 포함 될 수 있습니다.  
  
#### <a name="_core_to_add_dynamic_creation_support"></a> 동적 만들기 지원 기능을 추가 하려면  
  
1.  클래스를 파생 `CObject`합니다.  
  
2.  사용 된 `DECLARE_DYNCREATE` 클래스 선언에는 매크로입니다.  
  
3.  인수 (기본 생성자) 없이 생성자를 정의 합니다.  
  
4.  사용 하 여는 `IMPLEMENT_DYNCREATE` 클래스 구현 파일에는 매크로입니다.  
  
#### <a name="_core_to_add_serialization_support"></a> Serialization 지원을 추가 하려면  
  
1.  클래스를 파생 `CObject`합니다.  
  
2.  재정의 `Serialize` 멤버 함수입니다.  
  
    > [!NOTE]
    >  호출 하는 경우 `Serialize` 직접, 즉, 하지 않으려는 경우 다형 포인터를 통해 개체를 직렬화, 3-5 단계를 생략 합니다.  
  
3.  사용 된 `DECLARE_SERIAL` 클래스 선언에는 매크로입니다.  
  
4.  인수 (기본 생성자) 없이 생성자를 정의 합니다.  
  
5.  사용 하 여는 `IMPLEMENT_SERIAL` 클래스 구현 파일에는 매크로입니다.  
  
> [!NOTE]
>  클래스의 개체를 가리키는 "다형 포인터" (호출 A)는 (예 B)에서 파생 된 클래스의 개체 또는 합니다. 다형 포인터를 통해 serialize 하려면 프레임 워크는 일부 기본 클래스 (A)에서 파생 된 클래스의 개체 수 때문에 (B)을 직렬화은 개체의 런타임 클래스를 결정 해야 합니다.  
  
 클래스를 파생 하는 경우 직렬화를 사용 하는 방법에 대 한 자세한 내용은 `CObject`, 문서를 참조 [MFC의 파일](../mfc/files-in-mfc.md) 및 [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject에서 클래스 파생시키기](../mfc/deriving-a-class-from-cobject.md)
