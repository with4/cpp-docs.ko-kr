---
title: "컴파일러 오류 C3149 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3149
dev_langs: C++
helpviewer_keywords: C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 154ae99c5e47438f6fca3b85ac8318c1b14f7a30
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3149"></a>컴파일러 오류 C3149
'type': 최상위 'char' 없이 여기이 형식을 사용할 수 없습니다  
  
 선언이 올바르게 지정 하지 않았습니다.  
  
 예를 들어 수 정의 전역 범위에서 CLR 형식을 하 고 정의의 일부로 형식의 변수를 만들려고 합니다. CLR 형식의 전역 변수는 허용 되지 않으므로 C3149 컴파일러에서 생성 됩니다.  
  
 이 오류를 해결 하려면 형식 또는 함수 정의 내부 CLR 형식의 변수를 선언 합니다.  
  
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
