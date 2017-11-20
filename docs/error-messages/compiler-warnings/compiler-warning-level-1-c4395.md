---
title: "컴파일러 경고 (수준 1) C4395 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4395
dev_langs: C++
helpviewer_keywords: C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b45c77951e64f3ce0182f756ba2077ce49b5bd50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4395"></a>컴파일러 경고(수준 1) C4395
'function': 멤버 함수가 initonly 데이터 멤버 'member'의 복사본에서 호출 됩니다.  
  
 멤버 함수에서 호출한는 [initonly (C + + /cli CLI)](../../dotnet/initonly-cpp-cli.md) 데이터 멤버입니다.  C4395 경고 하는 **initonly** 함수에 의해 데이터 멤버를 수정할 수 없습니다.  
  
 다음 샘플에서는 C4395 오류가 생성 됩니다.  
  
```  
// C4395.cpp  
// compile with: /W1 /clr  
public value class V {  
public:  
   V(int data) : m_data(data) {}  
  
   void Mutate() {  
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);  
      m_data *= 2;  
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);  
   }  
  
   int m_data;  
};  
  
public ref class R {  
public:  
   static void f() {  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
      v.Mutate();   // C4395  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
   }  
  
private:  
   initonly static V v = V(4);  
};  
  
int main() {  
   R::f();  
}  
```