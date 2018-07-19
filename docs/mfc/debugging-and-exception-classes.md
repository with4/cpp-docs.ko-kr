---
title: 디버깅 및 예외 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9adf6a585771336de9fb33abbebdd6bab97383ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341763"
---
# <a name="debugging-and-exception-classes"></a>디버깅 및 예외 클래스
이러한 클래스는 동적 메모리 할당을 디버깅하고 예외가 throw된 함수에서 예외가 catch된 함수로 예외 정보를 전달하기 위한 지원을 제공합니다.  
  
 클래스를 사용 하 여 [CDumpContext](../mfc/reference/cdumpcontext-class.md) 및 [CMemoryState](../mfc/reference/cmemorystate-structure.md) 에 설명 된 대로 디버깅을 지원 하기 위해 개발 중 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다. 사용 하 여 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 문서에 설명 된 대로 실행 시 모든 개체의 클래스를 확인 하려면 [런타임 클래스 정보 액세스](../mfc/accessing-run-time-class-information.md)합니다. 프레임워크는 `CRuntimeClass`를 사용해서 특정 클래스의 개체를 동적으로 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

