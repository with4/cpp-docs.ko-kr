---
title: "컴파일러 오류 C3006 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3006
dev_langs: C++
helpviewer_keywords: C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1ea6ba0757da761aa8c431730f5bd7886270ccf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3006"></a>컴파일러 오류 C3006
'clause': OpenMP 'directive' 지시문의 절에 필요한 인수가 없습니다.  
  
 OpenMP 지시문에 필요한 인수가 없습니다.  
  
 다음 샘플에서는 C3006을 생성합니다.  
  
```  
// C3006.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel shared   // C3006  
   // Try the following line instead:  
   // #pragma omp parallel shared(x) {}  
  
}  
```