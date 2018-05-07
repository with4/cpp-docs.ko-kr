---
title: 코드 마법사를 사용 하지 않고 컨트롤에 대 한 형식이 안전한 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb861995c16411bb58e3051c5ffc78f75931ae8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행
첫 번째는 방식은 컨트롤에 대 한 형식이 안전한 액세스는 인라인 멤버 함수를 사용 하 여 클래스의 반환 형식을 캐스팅 `CWnd`의 `GetDlgItem` 멤버 함수를 다음이 예제와 같이 적절 한 c + + 컨트롤 형식:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 그런 다음 다음과 유사한 코드 형식이 안전한 방식으로 컨트롤에 액세스 하려면이 멤버 함수를 사용할 수 있습니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자에서 컨트롤에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행](../mfc/type-safe-access-to-controls-with-code-wizards.md)

