---
title: "컴파일러 오류 C3001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3001
dev_langs:
- C++
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bd853b18d53684237481791002d6089b1b664cfb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3001"></a>컴파일러 오류 C3001
'error_text': OpenMP 지시문 이름이 필요합니다.  
  
 `omp` pragma 뒤에 지시문이 와야 합니다.  
  
 다음 샘플에서는 C3001을 생성합니다.  
  
```  
// C3001.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp   // C3001 missing token  
}  
```
