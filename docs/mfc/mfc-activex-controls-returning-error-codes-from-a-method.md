---
title: 'MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdcd18a80b430a0a8576effaaa46215dd5eb9600
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36927921"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환
이 문서에서는 ActiveX 컨트롤 메서드에서 오류 코드를 반환 하는 방법을 설명 합니다.  
  
 하려면 메서드 내에서 오류가 발생 했음을 알리는 사용 해야는 [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) 멤버 함수를 매개 변수로 SCODE (상태 코드)를 사용 합니다. 미리 정의 된 SCODE를 사용 하거나 자체를 정의할 수 있습니다.  
  
> [!NOTE]
>  `ThrowError` 속성의 Get 또는 Set 내에서 오류를 반환 하는 방법 으로만 사용 하려는 함수 또는 메서드 자동화 합니다. 이 스택에 적절 한 예외 처리기 수 있는 시간을 제공 합니다.  
  
 도우미 함수는 가장 일반적인 같은 미리 정의 된 SCODEs에 대 한 존재 [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), 및 [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 미리 정의 된 SCODEs에 대 한 지침은 사용자 지정 SCODEs 정의 목록에 대 한 섹션을 참조 [Your ActiveX 컨트롤에 대 한 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX 컨트롤의: 고급 항목입니다.  
  
 코드의 다른 영역에서 예외 보고에 대 한 자세한 내용은 참조 하십시오. [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 섹션 [Your ActiveX 컨트롤에 대 한 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX 컨트롤의: 고급 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

