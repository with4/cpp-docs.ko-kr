---
title: "컴파일러 경고 (수준 1) C4742 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4742"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4742"
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4742
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var'의 맞춤이 'file1'과\(와\) 'file2'에서 서로 다릅니다\(number \- number\).  
  
 두 파일에서 참조하거나 정의한 외부 변수의 맞춤이 각 파일에서 서로 다릅니다.  이 경고는 *file1*의 변수에 대한 `__alignof`가 *file2*의 변수에 대한 `__alignof`와 다르다는 사실을 컴파일러가 발견한 경우에 발생합니다.  이러한 상황은 다른 파일에서 변수를 선언할 때 호환되지 않는 형식을 사용하거나 서로 다른 파일에서 일치하지 않는 `#pragma pack`을 사용하는 경우에 발생할 수 있습니다.  
  
 이 경고를 해결하려면 변수에 서로 다른 이름을 사용하거나 동일한 형식 정의를 사용해야 합니다.  
  
 자세한 내용은 [pack](../../preprocessor/pack.md) 및 [\_\_alignof 연산자](../../cpp/alignof-operator.md)를 참조하십시오.  
  
## 예제  
 다음은 형식을 정의하는 첫 번째 파일입니다.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## 예제  
 다음 샘플에서는 C4742 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```