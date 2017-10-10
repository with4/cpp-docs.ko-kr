---
title: "컴파일러 오류 C3011 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3011
dev_langs:
- C++
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f6405d987a617ed2bcf9dde2276b1190d831a7c8
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3011"></a>컴파일러 오류 C3011
병렬 영역 내부에서는 직접 인라인 어셈블리를 사용할 수 없습니다.  
  
 `omp` 병렬 영역은 인라인 어셈블리 명령을 포함할 수 없습니다.  
  
 다음 샘플에서는 C3011을 생성합니다.  
  
```  
// C3011.cpp  
// compile with: /openmp  
// processor: /x86  
int main() {  
   int   n = 0;  
  
   #pragma omp parallel  
   {  
      _asm mov eax, n   // Delete this line to resolve this error.  
   }   // C3011  
}  
```
