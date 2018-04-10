---
title: 프로토타입화 되지 않은 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 574c4564394e251dde9345d3658304019dae838d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="unprototyped-functions"></a>프로토타입화되지 않은 함수
함수의 완전히 프로토타입화 되지 않은 경우 호출자에 게 배정밀도로 정수 및 부동 소수점 값으로 정수 값을 전달 됩니다. 부동 소수점 값을 정수 레지스터와 부동 소수점 레지스터에 모두 포함 됩니다 부동 소수점 값 호출 수신자에 게 정수 레지스터의 값이 필요한 경우.  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)