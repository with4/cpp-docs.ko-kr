---
title: "컴파일러 오류 C3058 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3058
dev_langs:
- C++
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0e8d665e473877ac78612ccaeb9e2e917ee4094c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3058"></a>컴파일러 오류 C3058
'symbol': 기호를 'copyin' 절에 사용하기 전에 'threadprivate'로 선언하지 않았습니다.  
  
 기호를 먼저 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 로 선언해야 [copyin](../../parallel/openmp/reference/copyin.md) 절에 사용할 수 있습니다.  
  
 다음 샘플에서는 C3058을 생성합니다.  
  
```  
// C3058.cpp  
// compile with: /openmp  
int x, y, z;  
#pragma omp threadprivate(x, z)  
  
void test() {  
   #pragma omp parallel copyin(x, y)   // C3058  
   {  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C3058b.cpp  
// compile with: /openmp /LD  
int x, y, z;  
#pragma omp threadprivate(x, y)  
  
void test() {  
   #pragma omp parallel copyin(x, y)  
   {  
   }  
}  
```
