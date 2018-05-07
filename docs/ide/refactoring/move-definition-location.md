---
title: 정의 위치 이동 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44211105429e33c136999a7877ac6ee42af29f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="move-definition-location"></a>정의 위치 이동
**:** 즉시 해당 헤더 파일에 함수 정의 이동할 수 있습니다.

**경우:** 를 헤더 파일로 이동 하려는 함수가 있습니다.  

**이유:** 함수를 수동으로 이동 수 있지만이 기능은 됩니다 이동할 자동으로 필요한 경우 헤더 파일을 만드는 합니다.

**방법:**

1. 이동 하려는 함수를 통해 텍스트 또는 마우스 커서를 놓습니다.

   ![강조 표시된 코드](images/movedefinition_highlight.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.** 를 눌러 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **정의 위치 이동** 상황에 맞는 메뉴에서 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택 **정의 위치 이동** 상황에 맞는 메뉴에서 합니다.

1. 함수는 팝업 미리 보기 창에 표시 되 고 해당 헤더 파일에 이동 됩니다.  헤더 파일이 경우 것도 만들어지고 됩니다는 프로젝트에 배치 합니다.

   ![선언을 정의 /](images/movedefinition_result.png)
