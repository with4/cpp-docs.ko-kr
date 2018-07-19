---
title: 모달 및 모덜리스 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4f03d67e1eb9962f4303694db4850e800151404
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346563"
---
# <a name="modal-and-modeless-dialog-boxes"></a>모달 및 모덜리스 대화 상자
클래스를 사용할 수 [CDialog](../mfc/reference/cdialog-class.md) 두 종류의 대화 상자를 관리 하려면:  
  
-   *모달 대화 상자*, 사용자가 프로그램을 계속 하려면 응답 해야  
  
-   *모덜리스 대화 상자*, 다른 사용자 작업을 허용 하지만 화면에 언제 든 지 사용 하기 위해 사용할 수 있는  
  
 리소스 편집 및 대화 상자 템플릿을 만들기 위한 절차 모달 및 모덜리스 대화 상자에 대해 동일 합니다.  
  
 프로그램에 대 한 대화 상자 만들기의 다음 단계로 구성 됩니다.  
  
1.  사용 하 여 [대화 상자 편집기](../windows/dialog-editor.md) 대화 상자를 디자인 하 고 해당 대화 상자 템플릿 리소스를 만들어야 합니다.  
  
2.  대화 상자 클래스를 만듭니다.  
  
3.  연결 된 [메시지 처리기에 대화 상자 리소스 컨트롤](../windows/adding-event-handlers-for-dialog-box-controls.md) 대화 상자 클래스에 있습니다.  
  
4.  데이터 멤버를 지정 하려면 대화 상자의 컨트롤와 관련 된 추가 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md) 및 [대화 상자 데이터 유효성 검사 과정](../mfc/dialog-data-validation.md) 컨트롤에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

