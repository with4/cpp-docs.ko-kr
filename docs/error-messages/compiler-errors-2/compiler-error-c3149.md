---
title: "컴파일러 오류 C3149 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 555b3a7ac8e0d1e5de8eacd763c9ee63101e5b78
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3149"></a>컴파일러 오류 C3149
'type': 최상위 'char' 없이 여기이 형식을 사용할 수 없습니다  
  
 선언 올바르게 지정 되지 않았습니다.  
  
 예를 들어 수 정의 전역 범위에서 CLR 형식을 하 고 정의의 일부로 형식의 변수를 만들려고 합니다. CLR 형식의 전역 변수 허용 되지 않기 때문에 컴파일러 c&3149;가 발생 합니다.  
  
 이 오류를 해결 하려면 함수 또는 형식 정의 내 CLR 형식의 변수를 선언 합니다.  
  
 다음 샘플에서는 C3149 오류가 생성 됩니다.  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 다음 샘플에서는 C3149 오류가 생성 됩니다.  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  

