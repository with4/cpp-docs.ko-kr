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
ms.openlocfilehash: d2d45de1c6bd986c2bf509ce601f80fcd3721599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC에 RichEdit 1.0 컨트롤 사용
RichEdit 컨트롤을 사용 하려면 호출 먼저 해야 [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 컨트롤 (RICHED20 로드 하지. DLL)를 호출 하거나 [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) 를 이전에 RichEdit 1.0 컨트롤 (RICHED32 로드. DLL)입니다.  
  
 현재 사용할 수 있습니다 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 이전 RichEdit 1.0 컨트롤을 사용 하 여 클래스 하지만 **CRichEditCtrl** 2.0 RichEdit 컨트롤을 지원 하도록 디자인 되었습니다. 유사 하기 때문에 RichEdit 1.0 및 2.0 RichEdit 매우, 대부분의 메서드와; 작동 합니다. 그러나 1.0 및 2.0 컨트롤 몇 가지 방법을 제대로 작동 하지 않을 수 있습니다 또는 전혀 작동 하지 하므로 간에 약간 차이가 note 합니다.  
  
## <a name="requirements"></a>요구 사항  
 MFC  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 편집기 문제 해결](../windows/troubleshooting-the-dialog-editor.md)   
 [대화 상자 편집기](../windows/dialog-editor.md)

