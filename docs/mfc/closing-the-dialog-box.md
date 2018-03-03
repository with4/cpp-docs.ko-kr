---
title: "대화 상자 닫기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4c311a8d09ac3e1329b495fc321028e9f674993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="closing-the-dialog-box"></a>대화 상자 닫기
확인 단추 또는 "취소" 단추가 단추 중 하나 선택 하면 모달 대화 상자를 닫습니다. 확인 또는 취소 단추를 선택 하면 창이 대화 개체는 **BN_CLICKED** 단추와 컨트롤 알림 메시지의 ID, 하거나 **IDOK** 또는 **IDCANCEL**합니다. `CDialog`이러한 메시지에 대 한 기본 처리기 함수를 제공: `OnOK` 및 `OnCancel`합니다. 기본 처리기 호출의 `EndDialog` 멤버 함수를 대화 상자 창을 닫습니다. 호출할 수도 있습니다 `EndDialog` 사용자 고유의 코드에서. 자세한 내용은 참조는 [EndDialog](../mfc/reference/cdialog-class.md#enddialog) 클래스의 멤버 함수 `CDialog` 에 *MFC 참조*합니다.  
  
 재정의 닫고 삭제 모덜리스 대화 상자에 대 한 정렬 하려면 `PostNcDestroy` 호출 하 고는 **삭제** 연산자에는 **이** 포인터입니다. [대화 상자 제거](../mfc/destroying-the-dialog-box.md) 다음에 대해 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

