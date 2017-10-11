---
title: "컴파일러 오류 C2665 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5a349df2c60d746b6b090953362c7c6801e1f2a3
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2665"></a>컴파일러 오류 C2665
'function': 'type' 형식에서 매개 변수 번호 2를 변환할 수는 번호 1 오버 로드가  
  
 오버 로드 된 함수의 매개 변수에 필요한 형식으로 변환할 수 없습니다.  가능한 해결 방법:  
  
-   변환 연산자를 제공 합니다.  
  
-   명시적 변환을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2665 오류가 발생 합니다.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```
