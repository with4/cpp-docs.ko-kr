---
title: 컴파일러 오류 C3058 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3058
dev_langs:
- C++
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 867dbdead4c4268035b5c34a5ef053b959c822a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246677"
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