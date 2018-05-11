---
title: 모덜리스 대화 상자 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2055312c7418b14c9b274649db8faa297554257e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-modeless-dialog-boxes"></a>모덜리스 대화 상자 만들기
모덜리스 대화 상자에 대 한 대화 상자 클래스에 사용자 고유의 공용 생성자를 제공 해야 합니다. 모덜리스 대화 상자를 만들려면 공용 생성자를 직접 호출 하 고 다음 대화 상자 개체 [만들기](../mfc/reference/cdialog-class.md#create) 멤버 함수를 대화 상자 리소스를 로드 합니다. 호출할 수 있습니다 **만들기** 중 이나 후 생성자 호출 합니다. 대화 상자 리소스 속성에 있으면 **WS_VISIBLE**, 대화 상자가 바로 표시 됩니다. 호출 해야 합니다는 그렇지 않은 경우 해당 [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

