---
title: "컴파일러 오류 C3034 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3034
dev_langs: C++
helpviewer_keywords: C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65db8f94bbc6a37ded8a566e52acd7370037863a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3034"></a>컴파일러 오류 C3034
OpenMP 'directive1' 지시문은 'directive2' 지시문 내부에 직접 중첩될 수 없습니다.  
  
 일부 지시문은 중첩될 수 없습니다. 이 오류를 해결하려면 두 지시문의 문을 하나의 지시문 블록으로 병합하거나 연속 지시문을 생성할 수 있습니다.  
  
 다음 샘플에서는 C3034를 생성합니다.  
  
```  
// C3034.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
  
   #pragma omp single  
   {  
      #pragma omp single   // C3034   
      {  
      ;  
      }  
   }  
  
   // Two consecutive single clauses are OK.  
   #pragma omp single  
   {  
   }  
  
   #pragma omp single  
   {  
   }  
}  
```