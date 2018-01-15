---
title: "MFC ActiveX 컨트롤: 고급 속성 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ac8b2cb1a9c8de43ecfbd2f4712d19750bb143a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX 컨트롤: 고급 속성 구현
이 문서에서는 ActiveX 컨트롤에 고급 속성을 구현 하는 데 관련 된 항목을 설명 합니다.  
  
-   [쓰기 전용 및 읽기 전용 속성](#_core_read2donly_and_write2donly_properties)  
  
-   [속성에서 오류 코드 반환](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a>쓰기 전용 및 읽기 전용 속성  
 속성 추가 마법사는 컨트롤에 대 한 읽기 전용 이거나 쓰기 전용 속성을 구현 하는 빠르고 쉬운 메서드를 제공 합니다.  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>읽기 전용 이거나 쓰기 전용 속성을 구현 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **속성 추가**합니다.  
  
     열립니다는 [속성 추가 마법사](../ide/names-add-property-wizard.md)합니다.  
  
5.  에 **속성 이름** 사용자 속성의 이름을 입력 합니다.  
  
6.  **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.  
  
7.  에 **속성 형식** 상자에서 속성에 대 한 적절 한 형식을 선택 합니다.  
  
8.  읽기 전용 속성을 사용 하도록 하려는 경우에 Set 함수 이름의 선택을 취소 합니다. 쓰기 전용 속성을 사용 하도록 하려는 경우에 Get 함수 이름의 선택을 취소 합니다.  
  
9. **마침**을 클릭합니다.  
  
 이렇게 하면 속성 추가 마법사는 함수를 삽입 하는 `SetNotSupported` 또는 `GetNotSupported` 함수를 가져오거나 대신 일반 디스패치 맵 항목에 설정 합니다.  
  
 기존 속성을 읽기 전용 또는 쓰기 전용일 수를 변경 하려는 경우 디스패치 맵을 수동으로 편집 하 고 control 클래스에서 불필요 한 Set 또는 Get 함수를 제거할 수 있습니다.  
  
 속성 조건에 따라 읽기 전용 또는 쓰기 전용일 수 (예: 컨트롤 특정 모드에서 작동 하는 경우에)을 원하는 경우에 Set 또는 Get 함수 정상적으로 제공를 호출할 수 있습니다는 `SetNotSupported` 또는 `GetNotSupported` 적절 한 작동 합니다. 예:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 이 코드 샘플에서는 호출 `SetNotSupported` 경우는 `m_bReadOnlyMode` 데이터 멤버는 **TRUE**합니다. 경우 **FALSE**, 속성은 새 값으로 설정 합니다.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a>속성에서 오류 코드 반환  
 속성을 가져오거나 설정 하는 동안 오류가 발생 했음을 알리는를 사용 하 여는 `COleControl::ThrowError` 함수를 사용는 `SCODE` (상태 코드)를 매개 변수로 합니다. 미리 정의 된 사용할 수 있습니다 `SCODE` 하거나 자체를 정의 합니다. 목록은 미리 정의 된 `SCODE`s 및 사용자 지정을 정의 하기 위한 지침 `SCODE`s, 참조 [Your ActiveX 컨트롤에 대 한 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) 문서 ActiveX 컨트롤의: 고급 항목입니다.  
  
 도우미 함수에 대 한 미리 정의 된 가장 일반적인 존재 `SCODE`s와 같은 [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), 및 [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted)합니다.  
  
> [!NOTE]
>  `ThrowError`속성의 Get 또는 Set 내에서 오류를 반환 하는 방법 으로만 사용 하려는 함수 또는 자동화 메서드. 이 스택에 적절 한 예외 처리기 수 있는 시간을 제공 합니다.  
  
 코드의 다른 영역에서 예외 보고에 대 한 자세한 내용은 참조 하십시오. [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 섹션 [Your ActiveX 컨트롤에 대 한 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) 문서의 ActiveX 컨트롤: 고급 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)   
 [COleControl 클래스](../mfc/reference/colecontrol-class.md)
