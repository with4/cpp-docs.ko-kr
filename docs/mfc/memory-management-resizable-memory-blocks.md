---
title: '메모리 관리: 크기 조정 가능한 메모리 블록 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bbd97899261f85454824fcab261d330b04e25fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="memory-management-resizable-memory-blocks"></a>메모리 관리: 크기 조정 가능한 메모리 블록
**새** 및 **삭제** 연산자, 문서에 설명 된 [메모리 관리: 예](../mfc/memory-management-examples.md)는 것이 좋지만 할당 및 고정 크기의 메모리 블록을 취소 하 고 개체입니다. 경우에 따라서는 응용 프로그램 크기 조정 가능한 메모리 블록을 할 수 있습니다. 표준 C 런타임 라이브러리 함수를 사용 해야 [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), 및 [무료](../c-runtime-library/reference/free.md) 힙의 크기 조정 가능한 메모리 블록을 관리할 수 있습니다.  
  
> [!IMPORTANT]
>  혼합 된 **새** 및 **삭제** MFC의 디버그 버전에서 손상 된 메모리의 크기 조정 가능한 메모리 할당 함수 동일한 메모리 블록에 있는 연산자 발생 합니다. 사용 하지 않아야 `realloc` 로 할당 된 메모리 블록에 **새**합니다. 마찬가지로, 인 메모리 블록을 할당 하지 해야는 **새** 연산자 및 사용 하 여 삭제 **무료**, 사용 또는 **삭제** 로할당된메모리의블록에서연산자`malloc`.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)

