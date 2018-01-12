---
title: "모달 대화 상자 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 815db891514eb03169dac2ad29e50469d74dcfee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modal-dialog-boxes"></a>모달 대화 상자 만들기
모달 대화 상자를 만들려면에 선언 된 두 public 생성자 중 하나를 호출 [CDialog](../mfc/reference/cdialog-class.md)합니다. 그런 다음 호출 하는 대화 상자 개체 [DoModal](../mfc/reference/cdialog-class.md#domodal) 멤버 함수를 대화 상자를 표시 하 고 사용자가 확인 될 때까지 상호 작용을 관리 하거나 취소 합니다. 이 관리는 `DoModal`을 사용하여 대화 상자 모달을 만듭니다. 모달 대화 상자에 대해 `DoModal`에서는 대화 상자 리소스를 로드합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

