---
title: "컴파일러 경고 (수준 1) C4028 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4028
dev_langs: C++
helpviewer_keywords: C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 757db68ce894f82064f1635451255a266747a14d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4028"></a>컴파일러 경고 (수준 1) C4028
'number' 선언에서 다른 형식 매개 변수  
  
 형식 매개 변수의 형식 선언에서 해당 매개 변수와 함께 일치 하지 않습니다. 원래 선언에 형식이 사용 됩니다.  
  
 이 경고 C 소스 코드에 대해서만 유효합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4028 오류가 발생 합니다.  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```