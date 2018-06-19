---
title: 스택 및 큐 컬렉션 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC collection classes [MFC], stack collections
- collections, stack
- stack
- collection classes [MFC], creating
- queue collections
- MFC collection classes [MFC], queue collections
- stack collections
- collections, queue
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5545a1803675965cdea716e009ab70d2d72a31f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345715"
---
# <a name="creating-stack-and-queue-collections"></a>스택 및 큐 컬렉션 만들기
이 문서와 같은 기타 데이터 구조를 만드는 방법에 설명 [스택](#_core_stacks) 및 [큐](#_core_queues), MFC에서 클래스를 나열 합니다. 파생 된 클래스를 사용 하는 예제 `CList`, 하지만 사용할 수 있습니다 `CList` 직접 기능을 추가 하는 제외 합니다.  
  
##  <a name="_core_stacks"></a> 스택  
 표준 목록 컬렉션 앞면과 뒷면 모두이 이기 때문에 마지막에서 첫 번째 아웃 스택의 동작을 모방 하는 파생 된 목록 컬렉션을 만들 쉽습니다. 스택 식당에 접시 더미와 비슷합니다. 트레이 스택에 추가 되 면 스택 맨 위에 이동 합니다. 마지막에 추가한 접시 제거할 첫 번째 단원입니다. 목록 컬렉션 멤버 함수 `AddHead` 및 `RemoveHead` 목록의 헤드에서 구체적으로 요소를 제거를 따라서 가장 최근에 추가 된 요소는 제거 될 첫 번째 및 추가 하려면 사용할 수 있습니다.  
  
#### <a name="to-create-a-stack-collection"></a>스택 컬렉션을 만들려면  
  
1.  기존 MFC 목록 클래스 중 하나에서 새 목록 클래스를 파생 하 고 스택 작업의 기능을 지 원하는 다른 멤버 함수를 추가 합니다.  
  
     다음 예제에서는 요소는 스택의 맨 위에 있는 요소를 미리 볼 스택에 푸시한 맨 위에 있는 요소 스택에서 팝 하는 멤버 함수를 추가 하는 방법을 보여 줍니다.  
  
     [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]  
  
 이 방법은 기본을 노출 하는 참고 `CObList` 클래스입니다. 사용자를 호출할 수 `CObList` 멤버 함수를 있는지 여부는 스택에 대 한 것이 좋습니다.  
  
##  <a name="_core_queues"></a> 큐  
 표준 목록 컬렉션 앞면과 뒷면 모두 있어서 쉽게 선입 선출 큐의 동작을 모방 하는 파생 된 목록 컬렉션을 만들 수 이기도 합니다. 큐는 식당에는 사용자의 줄 비슷합니다. 줄에 첫 번째 사용자는 첫 번째 서비스할 수입니다. 더 많은 사람들이으로 순서를 대기 하는 줄의 끝으로 이동 합니다. 목록 컬렉션 멤버 함수 `AddTail` 및 `RemoveHead` 추가 하는 데 사용 될 및 특히 h e a d 또는 목록 꼬리에서 요소를 제거할; 따라서 가장 최근에 추가 된 요소는 항상 마지막으로 제거할 수 있습니다.  
  
#### <a name="to-create-a-queue-collection"></a>큐 컬렉션을 만들려면  
  
1.  Microsoft Foundation Class 라이브러리와 함께 제공 되는 미리 정의 된 목록 클래스 중 하나에서 새 목록 클래스를 파생 하 고 큐 작업의 의미 체계를 지원 하기 위해 더 많은 멤버 함수를 추가 합니다.  
  
     다음 예에서는 큐의 끝에 요소를 추가 하 고 큐의 앞에서 요소를 가져오는 하는 멤버 함수 추가 수 하는 방법을 보여 줍니다.  
  
     [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션](../mfc/collections.md)

