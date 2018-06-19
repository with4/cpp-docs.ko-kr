---
title: CObject에서 클래스를 파생 | Microsoft Docs
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
- DECLARE_DYNCREATE macro [MFC]
- DECLARE_SERIAL macro [MFC]
- macros [MFC], serialization
- serialization [MFC], macros
- DECLARE_DYNAMIC macro [MFC]
- derived classes [MFC], from CObject
- CObject class [MFC], deriving serializable classes
- CObject class [MFC], deriving from
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0b629617c1592387f3f959996fd3e9837242ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349359"
---
# <a name="deriving-a-class-from-cobject"></a>CObject에서 클래스 파생시키기
이 문서에서 클래스를 파생 하는 데 필요한 최소 단계에서는 설명 [CObject](../mfc/reference/cobject-class.md)합니다. 다른 `CObject` 클래스 문서 특정 기능을 활용 하는 데 필요한 단계를 설명 `CObject` serialization 진단 디버깅 지원 등의 기능입니다.  
  
 토론에 `CObject`, 용어 "인터페이스 file" 및 "구현 파일" 자주 사용 됩니다. 인터페이스 파일 (라고도 하는 헤더 파일 또는 합니다. H 파일)는 클래스 선언 및 클래스를 사용 하는 데 필요한 기타 정보를 포함 합니다. 구현 파일 (또는 합니다. CPP 파일)에서 클래스 멤버 함수를 구현 하는 코드 뿐 아니라 클래스 정의 포함 합니다. 클래스에 대 한 예를 들어 `CPerson`, 일반적으로 PERSON 이라는 하는 인터페이스 파일을 만듭니다. H와 구현 파일 PERSON을 이라는 합니다. CPP 합니다. 그러나 응용 프로그램 간에 공유할 수는 몇 가지 작은 클래스에 대 한 것이 더 쉽습니다 인터페이스와 구현 파일 단일 결합 합니다. CPP 파일입니다.  
  
 클래스를 파생 하는 경우 네 가지 수준의 기능에서 선택할 수 있습니다 `CObject`:  
  
-   기본 기능: 런타임 클래스 정보 또는 serialization 지원 되지 않지만 진단 메모리 관리를 포함 합니다.  
  
-   기본 기능 런타임 클래스 정보에 대 한 지원을 포함 합니다.  
  
-   실행 시간에 대 한 지원을 포함 하는 기본 기능 클래스 정보 및 동적 생성 합니다.  
  
-   기본 기능 런타임 클래스 정보, 동적 생성 및 serialization에 대 한 지원을 포함 합니다.  
  
 (나중에 기본 클래스로 사용 됩니다 하) 다시 사용 하기 위해 설계 된 클래스 앞으로 serialization 필요 함을 예측 런타임 클래스 지원과 serialization 지원의 포함 이상 되어야 합니다.  
  
 선언 및에서 파생 클래스의 구현에서 특정 선언 및 구현 매크로 사용 하 여 기능 수준을 선택 `CObject`합니다.  
  
 다음 표에서 serialization 및 런타임 정보를 지 원하는 데 사용 되는 매크로 간의 관계를 보여 줍니다.  
  
### <a name="macros-used-for-serialization-and-run-time-information"></a>Serialization 및 런타임 정보에 사용 되는 매크로  
  
|매크로 사용|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|  
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|  
|기본 `CObject` 기능|아니요|아니요|아니요|  
|`DECLARE_DYNAMIC`|예|아니요|아니요|  
|`DECLARE_DYNCREATE`|예|예|아니요|  
|`DECLARE_SERIAL`|예|예|예|  
  
#### <a name="to-use-basic-cobject-functionality"></a>기본 CObject 기능을 사용 하려면  
  
1.  일반 c + + 구문을 사용 하 여에서 클래스를 파생 `CObject` (또는에서 파생 된 클래스에서 `CObject`).  
  
     다음 예제에서는 가장 간단한 경우에서 클래스를 파생 시키는 `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]  
  
 그러나 일반적으로의 일부를 재정의할 수도 `CObject`의 새 클래스의 세부 사항을 처리 하는 멤버 함수입니다. 예를 들어 재정의 하려는 일반적으로 `Dump` 의 기능은 `CObject` 클래스의 내용에 대 한 디버깅 출력을 제공 하 합니다. 재정의 하는 방법에 대 한 내용은 `Dump`, 문서를 참조 [진단: 개체 내용을 덤프](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59)합니다. 재정의 하려면는 `AssertValid` 의 기능은 `CObject` 클래스 개체의 데이터 멤버의 일관성을 확인 하는 사용자 지정 된 테스트 수 있도록 합니다. 에 대 한 설명은 재정의 하는 방법 `AssertValid`, 참조 [MFC ASSERT_VALID 및 CObject::AssertValid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6)합니다.  
  
 문서 [기능 수준 지정](../mfc/specifying-levels-of-functionality.md) 다른 수준의 런타임 클래스 정보, 동적 개체 만들기 및 serialization을 포함 한 기능을 지정 하는 방법에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 사용](../mfc/using-cobject.md)

