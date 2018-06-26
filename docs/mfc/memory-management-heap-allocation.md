---
title: '메모리 관리: 힙 할당 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7ef166201103b1544d0a36d82452b485af75418
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928611"
---
# <a name="memory-management-heap-allocation"></a>메모리 관리: 힙 할당
힙에 프로그램의 메모리 할당 요구 사항을 예약 되어 있습니다. 이 영역은 외에도 프로그램 코드와 스택 합니다. 함수를 사용 하 여 일반적인 C 프로그램 **malloc** 및 **무료** 할당 하 고 힙 메모리 할당을 취소 합니다. C + + 기본 제공 연산자의 수정 된 버전을 제공 하는 MFC의 디버그 버전 **새** 및 **삭제** 할당 하 고 힙 메모리에 개체 할당을 취소 합니다.  
  
 사용 하는 경우 **새** 및 **삭제** 대신 **malloc** 및 **무료**, 클래스 라이브러리의 기능을 활용할 수 메모리 관리 디버깅 기능을 향상 메모리 누수를 탐지 하는 데 유용할 수 있습니다. 릴리스 버전의 표준 버전의 MFC 사용 하 여 프로그램을 빌드할 때는 **새** 및 **삭제** 연산자 할당 하 고 릴리스 버전 (MFC 메모리 할당을 취소할 수 있는 효율적인 방법을 제공 이러한 연산자의 수정 된 버전 제공 하지 않습니다).  
  
 참고 힙에 할당 된 개체의 전체 크기 시스템의 사용 가능한 가상 메모리에 의해서만 제한 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 관리](../mfc/memory-management.md)

