---
title: ExitInstance 멤버 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 954d2248061ec571d9d2ba8804c1f7c97275cbfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exitinstance-member-function"></a>ExitInstance 멤버 함수
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 클래스의 멤버 함수 [CWinApp](../mfc/reference/cwinapp-class.md) 응용 프로그램의 복사본 종료 되 면 일반적으로 사용자는 응용 프로그램을 종료로 인해 될 때마다 호출 됩니다.  
  
 재정의 `ExitInstance` 그래픽 장치 GDI (인터페이스) 리소스를 해제 또는 프로그램 실행 중에 사용 되는 메모리 할당 해제와 같은 특별 한 정리 처리 해야 합니다. 그러나 표준 항목 예: 문서 및 뷰 정리 해당 개체에만 적용 되는 특별 한 정리를 수행 하는 데 재정의 가능한 다른 기능 프레임 워크에서 제공 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)
