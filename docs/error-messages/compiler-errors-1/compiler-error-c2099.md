---
title: "컴파일러 오류 C2099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 74fdc75470600c29029c52e38ab2073e484dbde6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2099"></a>컴파일러 오류 C2099
이니셜라이저가 상수가 아닙니다.  
  
 이 오류는 C 컴파일러에서만 나타나며, 자동이 아닌 변수에 대해서만 발생합니다.  컴파일러는 프로그램의 시작 부분에서 자동이 아닌 변수를 초기화하며 초기화된 값은 상수여야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2099를 생성합니다.  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>예제  
 컴파일러가 식에서 상수 폴딩을 수행할 수 없기 때문에 c 2099가 발생할 수도 있습니다 **/fp: strict** 부동 소수점 정밀도 환경 설정 때문에 (참조 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) 자세한 내용은) 런타임 컴파일과에서 다를 수 있습니다.  
  
 상수 폴딩이 실패하면 컴파일러가 동적 초기화를 호출하는데 이는 C에서는 허용되지 않습니다.  
  
 이 오류를 해결하려면 모듈을 .cpp 파일로 컴파일하거나 식을 단순화합니다.  
  
 자세한 내용은 [/fp(부동 소수점 동작 지정)](../../build/reference/fp-specify-floating-point-behavior.md)를 참조하세요.  
  
 다음 샘플에서는 C2099를 생성합니다.  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```
