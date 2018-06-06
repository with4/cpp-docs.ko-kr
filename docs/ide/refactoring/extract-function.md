---
title: 함수 추출 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fc4d48c972bca9352f326085574e4cf4df83aea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333159"
---
# <a name="extract-function"></a>함수 추출
**대상:** 코드 조각을 고유한 함수로 변환할 수 있습니다.

**시기:** 다른 함수에서 호출해야 하는 일부 함수에 기존 코드 조각이 있습니다.  

**이유:** 해당 코드를 복사하여 붙여넣을 수 있지만 중복이 발생합니다.  더 나은 솔루션은 다른 함수에서 자유롭게 호출할 수 있는 고유한 함수로 해당 조각을 리팩터링하는 것입니다.

**방법:**

1. 추출할 코드를 강조 표시합니다.

   ![강조 표시된 코드](images/extractfunction_highlight.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+R**을 누른 다음 **Ctrl+M**을 누릅니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * **Ctrl+.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 상황에 맞는 메뉴에서 **함수 추출(실험적)** 을 선택합니다.
   * **마우스**
     * **편집 > 리팩터링 > 함수 추출(실험적)** 을 선택합니다.
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, 상황에 맞는 메뉴에서 **함수 추출(실험적)** 을 선택합니다.
     * 왼쪽 여백에 나타나는 ![전구](images/bulb.png) 아이콘을 클릭하고, 상황에 맞는 메뉴에서 **함수 추출(실험적)** 을 선택합니다.

1. **함수/메서드 추출(실험적)** 창에서 새로운 함수 이름을 입력하고, 코드를 배치하려는 위치를 선택하고, **확인** 단추를 클릭합니다.  

   ![함수 추출 함수](images/extractfunction_dialog.png)

1. 새 함수는 사용자가 지정한 위치에서 생성되고, 함수는 해당하는 헤더 파일에 프로토타입으로 지정되고, 원본 코드는 해당 함수를 호출하도록 변경됩니다.

   ![함수 추출 결과](images/extractfunction_result.png)