---
title: 2.7.2.3 lastprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08f331862d6e48b1c0882382285ddffa9699e79c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687344"
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate
`lastprivate` 절에서 제공 하는 기능의 상위 집합을 제공 된 `private` 절. 구문은 `lastprivate` 절은 다음과 같습니다.  
  
```  
lastprivate(variable-list)  
```  
  
 에 지정 된 변수는 *변수 목록* 가 `private` 절 의미 합니다. 경우는 `lastprivate` 작업 공유 구문에 각각의 값을 식별 하는 지시문에 절이 나타납니다 `lastprivate` 관련된 루프 또는 어휘 적으로 마지막 섹션 지시문의 순차적으로 마지막 반복에서 변수가 할당 된는 변수의 원래 개체입니다. 마지막 반복에서 값이 할당 되지 않은 변수는 **에 대 한** 또는 **에 대 한 병렬**, 또는의 어휘 적으로 마지막 섹션에 **섹션** 또는  **섹션에서는 병렬** 지시문을 사용 하는 구문 후 비활성화 상태 값을 갖습니다. 할당 되지 않은 하위 개체는 또한는 구문을 후 결정 되지 않은 값을 갖습니다.  
  
 시의 제한 된 `lastprivate` 절은 다음과 같습니다.  
  
-   에 대 한 모든 제한을 `private` 적용 합니다.  
  
-   으로 지정 된 클래스 형식의 변수에 `lastprivate` 액세스 가능 하며 명확한 복사 할당 연산자가 있어야 합니다.  
  
-   변수 또는 개인 병렬 영역 내부에 표시 되는 `reduction` 절은 **병렬** 지시문에 지정할 수 없습니다는 `lastprivate` 는 병렬 구문에 바인딩하는 작업 공유 지시문의 절.