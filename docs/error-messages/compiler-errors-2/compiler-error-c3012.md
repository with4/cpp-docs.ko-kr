---
title: "컴파일러 오류 C3012 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e7cf30b5aa214c5042e430377cf839e463140149
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3012"></a>컴파일러 오류 C3012
'intrinsic': 병렬 영역 내부에서는 직접 내장 함수를 사용할 수 없습니다.  
  
 A [컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md) 함수에서 허용 되지 않는 한 `omp``parallel` 영역입니다.  
  
 다음 샘플에서는 C3012를 생성합니다.  
  
```  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C"  
{  
#endif  
  
void* _ReturnAddress();  
  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   _ReturnAddress();   // OK  
  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
}  
```
