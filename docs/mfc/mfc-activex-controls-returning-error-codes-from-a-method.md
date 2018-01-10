---
title: "MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환 | Microsoft Docs"
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
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5563153cdc5d90bc522c1f0b4edf48a8cc280755
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX 컨트롤: 메서드에서 오류 코드 반환
이 문서에서는 ActiveX 컨트롤 메서드에서 오류 코드를 반환 하는 방법을 설명 합니다.  
  
 하려면 메서드 내에서 오류가 발생 했음을 알리는 사용 해야는 [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) 를 사용 하는 멤버 함수는 `SCODE` (상태 코드)를 매개 변수로 합니다. 미리 정의 된 사용할 수 있습니다 `SCODE` 하거나 자체를 정의 합니다.  
  
> [!NOTE]
>  `ThrowError`속성의 Get 또는 Set 내에서 오류를 반환 하는 방법 으로만 사용 하려는 함수 또는 메서드 자동화 합니다. 이 스택에 적절 한 예외 처리기 수 있는 시간을 제공 합니다.  
  
 도우미 함수에 대 한 미리 정의 된 가장 일반적인 존재 `SCODE`s와 같은 [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), 및 [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted)합니다.  
  
 목록은 미리 정의 된 `SCODE`s 및 사용자 지정 정의 대 한 지침 `SCODE`s 섹션을 참조 [Your ActiveX 컨트롤에 대 한 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX 컨트롤의: 고급 항목입니다.  
  
 코드의 다른 영역에서 예외 보고에 대 한 자세한 내용은 참조 하십시오. [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) 및 섹션 [Your ActiveX 컨트롤에 대 한 오류 처리](../mfc/mfc-activex-controls-advanced-topics.md) ActiveX 컨트롤의: 고급 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

