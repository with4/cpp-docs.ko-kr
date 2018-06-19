---
title: '메모리 관리: 프레임 할당 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory leaks [MFC], frame allocation
- memory [MFC], detecting leaks
- memory [MFC], reclaiming
- memory allocation [MFC], frames
- frame variables [MFC], automatic deletion of
- scope [MFC], frame variables
- heap allocation [MFC], vs. frame allocation
- variables [MFC], frame variables
- memory leaks [MFC], detecting
- memory, releasing [MFC]
- stack frames [MFC]
- memory leaks [MFC], allocating objects on the frame
- detecting memory leaks [MFC]
- frame allocation [MFC]
- frame variables [MFC]
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f67149e5835ee6f2b8922b29ee92872b24d0ec4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349313"
---
# <a name="memory-management-frame-allocation"></a>메모리 관리: 프레임 할당
프레임 할당 설정 된 "스택 프레임"에서 해당 이름을 가진 때마다 함수를 호출 합니다. 스택 프레임은 일시적으로 인수를 보유 하는 정의 된 모든 변수 뿐만 아니라 함수에 함수에 로컬 메모리 영역입니다. 프레임 변수가 컴파일러에 대 한 공간을 자동으로 할당 하기 때문에 "자동" 변수 라고도 합니다.  
  
 프레임 할당의 두 가지 주요 특징 있습니다. 첫째, 지역 변수를 정의할 때 충분 한 공간이 할당 되지 전체 변수를 보유 하는 스택 프레임에 큰 배열 또는 데이터 구조를 경우에. 둘째, 프레임 변수가 범위를 벗어날 때 자동으로 삭제 됩니다.  
  
 [!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]  
  
 로컬 함수 변수에 대 한 중첩 된 중괄호를 사용 하는 경우 함수 종료 프레임 변수의 범위 되지만 함수 보다 작을 수 범위는이 전환이 발생 합니다. 프레임 변수의 자동 삭제 하는 것이 매우 중요 합니다. 간단한 기본 형식의 경우 (같은 `int` 또는 **바이트**), 배열 또는 데이터 구조를 자동으로 삭제할 변수에서 사용 되는 메모리를 간단 하 게 회수 합니다. 변수 범위를 벗어난 이후 계속 액세스할 수 없습니다. 그러나 c + + 개체의 경우 자동 삭제 과정은 좀 더 복잡 합니다.  
  
 개체를를 프레임 변수로 정의 해당 생성자 정의 발견 되는 지점에서 자동으로 호출 됩니다. 개체가 범위를 벗어나면 개체에 대 한 메모리를 회수 하기 전에 해당 소멸자가 자동으로 호출 됩니다. 이 자동 생성 및 소멸 매우 유용할 수 있지만 소멸자 특히 자동 호출이 알고 있어야 합니다.  
  
 프레임에 개체 할당의 주요 이점은 자동으로 삭제 된다는입니다. 프레임에서 개체를 할당 하는 경우 메모리 누수 잊어버린된 개체에 걱정할 필요가 없습니다. (메모리 누수에 대 한 세부 정보를 문서를 참조 하십시오. [MFC의 메모리 누수 탐지](http://msdn.microsoft.com/en-us/29ee8909-96e9-4246-9332-d3a8aa8d4658).) 프레임 할당의 단점은 범위 밖 프레임 변수를 사용할 수 없습니다. 프레임 할당과 힙 할당을 선택 하는 다른 요소는 큰 구조 및 개체에 대 한 하다는 종종 스택 공간이 제한 되어 종종 있으므로 저장소에 대 한 힙을 하면 스택 대신 사용 하 여 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 관리](../mfc/memory-management.md)

