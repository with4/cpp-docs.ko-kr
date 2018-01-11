---
title: "컴파일러 오류 C3009 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3009
dev_langs: C++
helpviewer_keywords: C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1fd939bb473c334b97a1fb65ff44042fe238417
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3009"></a>컴파일러 오류 C3009
'label': OpenMP 구조화된 블록 외부에서 내부로 점프할 수 없습니다.  
  
 코드가 OpenMP 블록 안이나 밖으로 점프할 수 없습니다.  
  
 다음 샘플에서는 C3009를 생성합니다.  
  
```  
// C3009.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel   
   {  
   lbl2:;  
   }  
   goto lbl2;   // C3009  
}  
```