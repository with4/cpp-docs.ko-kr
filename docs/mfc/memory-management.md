---
title: "메모리 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1350c4f41da4219ae2581f5e93cb95d03a65850
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="memory-management"></a>메모리 관리
다음이 문서에는의 MFC Microsoft Foundation 클래스 라이브러리 ()에 메모리 관리와 관련 된 일반적인 서비스를 활용 하는 방법을 설명 합니다. 메모리 할당은 두 가지 주요 범주로 나눌 수 있습니다: 프레임 할당과 힙 할당.  
  
 두 할당 방식의 주요 차이점 중 하나는 일반적으로 실제 메모리를 사용 하 여 작업할 프레임 할당 블록 자체를 힙 할당을 통해 항상 제공 됩니다 포인터 메모리 블록에 있는 동안은 합니다. 두 가지 구성표의 또 다른 주요 차이점은 된 프레임 개체는 자동으로 삭제, 프로그래머가 힙 개체를 명시적으로 삭제 해야 하는 동안 합니다.  
  
 Windows 용 프로그램에서 메모리 관리에 대 한 비 MFC 내용은 [메모리 관리](http://msdn.microsoft.com/library/windows/desktop/aa366779) Windows SDK에서 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [프레임 할당](../mfc/memory-management-frame-allocation.md)  
  
-   [힙 할당](../mfc/memory-management-heap-allocation.md)  
  
-   [배열에 대 한 메모리를 할당합니다.](../mfc/memory-management-examples.md)  
  
-   [힙에서 배열에 대 한 메모리를 할당 해제](../mfc/memory-management-examples.md)  
  
-   [데이터 구조에 대 한 메모리를 할당합니다.](../mfc/memory-management-examples.md)  
  
-   [개체에 대 한 메모리를 할당합니다.](../mfc/memory-management-examples.md)  
  
-   [크기 조정 가능한 메모리 블록](../mfc/memory-management-resizable-memory-blocks.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

