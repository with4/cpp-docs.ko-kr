---
title: 런타임 클래스 정보 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 947102f17a5f35b7e6b5266f637375982d4cd55f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334063"
---
# <a name="accessing-run-time-class-information"></a>런타임 클래스 정보 액세스
이 문서에서는 런타임에 개체의 클래스에 대 한 정보를 액세스 하는 방법을 설명 합니다.  
  
> [!NOTE]
>  MFC를 사용 하지 않습니다는 [런타임 형식 정보](../cpp/run-time-type-information.md) Visual c + + 4.0에서 도입 된 (RTTI) 지원 합니다.  
  
 클래스를 파생 시킨 경우 [CObject](../mfc/reference/cobject-class.md) 사용는 **DECLARE**_**동적** 및 `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE`, 또는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로 문서에서 설명 [CObject에서 클래스를 파생](../mfc/deriving-a-class-from-cobject.md), `CObject` 클래스에 런타임 시 개체의 정확한 클래스를 결정 하는 기능입니다.  
  
 이 기능은 추가 형식 함수 인수 검사가 필요할 때 및 개체의 클래스에 기반 하는 특수 한 용도의 코드를 작성 해야 하는 경우 가장 유용 합니다. 그러나이 방법은 권장 되지 않습니다 일반적으로 동일한 가상 함수의 기능 때문에 있습니다.  
  
 `CObject` 멤버 함수 `IsKindOf` 특정 개체가 지정된 된 클래스에 속하는 경우 또는 특정 클래스에서 파생 되는 경우를 확인 하기 위해 사용할 수 있습니다. 에 대 한 인수 `IsKindOf` 는 `CRuntimeClass` 개체를 사용 하 여 가져올 수 있습니다는 `RUNTIME_CLASS` 매크로 클래스의 이름으로 합니다.  
  
### <a name="to-use-the-runtimeclass-macro"></a>RUNTIME_CLASS 매크로 사용 하려면  
  
1.  사용 하 여 `RUNTIME_CLASS` 다음과 같이 클래스에 대 한 클래스의 이름으로 `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]  
  
 거의 런타임 클래스 개체에 직접 액세스 해야 합니다. 런타임 클래스 개체를 전달 하는 보다 일반적인 사용의 `IsKindOf` 다음 절차에 나와 있는 것 처럼 작동 합니다. `IsKindOf` 함수는 특정 클래스에 속해 있는지 확인 하는 개체를 테스트 합니다.  
  
#### <a name="to-use-the-iskindof-function"></a>IsKindOf 함수를 사용 하려면  
  
1.  클래스에 런타임 클래스 지원을 확인 합니다. 즉, 클래스 해야에서 파생 된 직접 또는 간접적으로 `CObject` 사용는 **DECLARE**_**동적** 및 `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` 및 `IMPLEMENT_DYNCREATE`, 또는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로 문서에서 설명 [CObject에서 클래스를 파생](../mfc/deriving-a-class-from-cobject.md)합니다.  
  
2.  호출 된 `IsKindOf` 해당 클래스의 개체에 대 한 멤버 함수를 사용 하는 `RUNTIME_CLASS` 생성 하는 매크로 `CRuntimeClass` 인수를 다음과 같이:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  IsKindOf 반환 **TRUE** 개체가 지정된 된 클래스에서 파생 된 클래스 또는 지정된 된 클래스의 구성원입니다. `IsKindOf` 필요한 경우 Microsoft Foundation 클래스 파생된에 대해 다중 상속을 사용할 수 있지만 여러 상속 또는 가상 기본 클래스를 지원 하지 않습니다.  
  
 개체의 동적 생성 런타임 클래스 정보의 용도 중 하나입니다. 이 프로세스는 문서에 설명 된 [동적 개체 만들기](../mfc/dynamic-object-creation.md)합니다.  
  
 Serialization 중에 정보 및 런타임 클래스 정보를 자세한 문서를 참조 하십시오. [MFC의 파일](../mfc/files-in-mfc.md) 및 [Serialization](../mfc/serialization-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 사용](../mfc/using-cobject.md)

