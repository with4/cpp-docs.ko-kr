---
title: 컴파일러 오류 C3269 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3269
dev_langs:
- C++
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98e4e2a2df4271a3a0213b8abedc385f22c871aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3269"></a>컴파일러 오류 C3269
'function': 관리 되는 또는 WinRTtype의 멤버-함수는 '...'로 선언할 수 없습니다  
  
관리되는 클래스 멤버 함수와 WinRT 클래스 멤버 함수는 변수 길이 매개 변수 목록을 선언할 수 없습니다.  
  
다음 샘플에서는 C3269 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3269_2.cpp  
// compile with: /clr  
  
ref struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```  
