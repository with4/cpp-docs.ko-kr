---
title: 컴파일러 오류 C2088 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2088
dev_langs:
- C++
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d35b736c8945b71a53c4ac5b7372dfed642fed44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166626"
---
# <a name="compiler-error-c2088"></a>컴파일러 오류 C2088
'operator': ' s-k '에 대 한 잘못 되었습니다.  
  
 구조체 또는 공용 구조체에 대 한 연산자를 정의 하지 않았습니다. 이 오류 C 코드에 대해서만 유효합니다.  
  
 다음 샘플에서는 세 번 C2088를 생성합니다.  
  
```  
// C2088.c  
struct S {  
   int m_i;   
} s;  
  
int main() {  
   int i = s * 1;   // C2088  
   struct S s2 = +s;   // C2088  
   s++;   // C2088  
}  
```