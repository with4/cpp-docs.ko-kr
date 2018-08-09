---
title: MFC에 RichEdit 1.0 컨트롤 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a00642c1aefdce57c37723ef4daf23381cee3c13
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650750"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC에 RichEdit 1.0 컨트롤 사용
RichEdit 컨트롤을 사용 하려면 먼저 불러와야 [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 컨트롤 (RICHED20 로드 하려면. DLL)를 호출 하거나 [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) 이전에 RichEdit 1.0 컨트롤 (RICHED32 로드 하려면. DLL)입니다.  
  
 현재 사용할 수 있습니다 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 이전 RichEdit 1.0 컨트롤을 사용 하 여 클래스 이지만 `CRichEditCtrl` RichEdit 2.0 제어를 지원 하도록 디자인 되었습니다. RichEdit 1.0 및 2.0 RichEdit 매우 유사한 이기 때문에 대부분의 메서드와; 작동 합니다. 그러나 일부의 차이점이 1.0 및 2.0 컨트롤 간의 몇 가지 방법을 제대로 작동 하지 않을 수 있습니다 하거나 전혀 작동 하지 않음 note 합니다.  
  
## <a name="requirements"></a>요구 사항  
 MFC  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 편집기 문제 해결](../windows/troubleshooting-the-dialog-editor.md)   
 [대화 상자 편집기](../windows/dialog-editor.md)