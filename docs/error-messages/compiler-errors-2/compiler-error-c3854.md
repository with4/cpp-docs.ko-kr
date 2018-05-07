---
title: 컴파일러 오류 C3854 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3854
dev_langs:
- C++
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbaed18984dbcc06b976a367ef9911528792ce52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3854"></a>컴파일러 오류 C3854
함수에 '='의 왼쪽으로 식을 평가합니다. (한 함수는 l 값이 아님) 함수에 할당할 수 없습니다.  
  
 대 한 참조를 다시 초기화할 수 없습니다. 함수에 대 한 참조를 역참조 하 고 할당할 수 없습니다, rvalue가 함수를 생성 합니다. 따라서 함수에 대 한 참조를 통해 할당할 수 없습니다.  
  
 다음 샘플에서는 C3854 오류가 생성 됩니다.  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```