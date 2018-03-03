---
title: "2.7.2.1 개인 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a08faf39ab2f82d76a936c216ba6707bee5c240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="2721-private"></a>2.7.2.1 private
`private` 절 팀에서 각 스레드에 private 변수 목록에서 변수를 선언 합니다. 구문은 `private` 절은 다음과 같습니다.  
  
```  
private(variable-list)  
```  
  
 동작에 지정 된 변수는 `private` 절은 다음과 같습니다. 자동 저장 기간이 있는 새 개체는 구문에 대 한 할당 됩니다. 크기 및 새 개체의 맞춤 변수 유형에 의해 결정 됩니다. 이 할당은 팀의 각 스레드에 대해 한 번씩 발생 하 고 기본 생성자가 호출 하 고 필요한 경우 클래스 개체에 대 한 그렇지 않은 경우 초기 값은 비활성화 상태입니다.  변수에서 참조 하는 원본 개체 구문에는 시작 시 비활성화 상태 값은이 고, 해당 구문의 동적 범위 내에서 수정 하지 않아야 출구는 구문에서 확인할 수 없는 값이 합니다.  
  
 지시문 구문의 어휘 범위 내에서 변수 스레드에 의해 할당 된 새 private 개체를 참조 합니다.  
  
 시의 제한 된 `private` 절은 다음과 같습니다.  
  
-   에 지정 된 클래스 형식의 변수에 `private` 절에는 액세스 가능 하며 명확한 기본 생성자가 있어야 합니다.  
  
-   에 지정 된 변수는 `private` 절을 가져서는 안 한 **const**-없을 경우 자식이 포함 된 형식을 클래스 형식 정규화는 `mutable` 멤버입니다.  
  
-   에 지정 된 변수는 `private` 절 불완전 한 형식 또는 참조 형식이 있어야 합니다.  
  
-   에 표시 되는 변수는 `reduction` 절은 **병렬** 지시문에 지정할 수는 `private` 는 병렬 구문에 바인딩하는 작업 공유 지시문의 절.