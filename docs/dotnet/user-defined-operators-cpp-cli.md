---
title: "사용자 정의 연산자 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b02d6806abedb407d1c53ec8022e92983ce21d28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-operators-ccli"></a>사용자 정의 연산자(C++/CLI)
정적 멤버 또는 인스턴스 멤버 또는 전역 범위에서 관리 되는 형식에 대 한 사용자 정의 연산자는 허용 됩니다. 그러나 정적 연산자만는 Visual c + + 이외의 언어로 작성 된 클라이언트에 메타 데이터를 통해 액세스할 수 있습니다.  
  
 참조 형식에서 다음 중 하나 여야 합니다 정적 사용자 정의 연산자의 매개 변수 중 하나:  
  
-   핸들 (`type` ^) 바깥쪽 형식의 인스턴스로.  
  
-   참조 형식 간접 참조 (`type`^ & 또는 형식 ^ %) 바깥쪽 형식의 인스턴스에 대 한 핸들을 합니다.  
  
 값 형식에서 다음 중 하나 여야 합니다 정적 사용자 정의 연산자의 매개 변수 중 하나:  
  
-   바깥쪽 값 형식으로 동일한 형식이 아닙니다.  
  
-   포인터 유형 간접 참조 (`type`^) 바깥쪽 형식입니다.  
  
-   참조 형식 간접 참조 (`type`% 또는 `type`&)를 바깥쪽 형식입니다.  
  
-   참조 형식 간접 참조 (`type`^ % 또는 `type`^ &)를 핸들입니다.  
  
 다음과 같은 연산자를 정의할 수 있습니다.  
  
|연산자|단항/이항 Forms?|  
|--------------|--------------------------|  
|!|단항|  
|!=|이항|  
|%|이항|  
|&|단항 및 이항|  
|&&|이항|  
|*|단항 및 이항|  
|+|단항 및 이항|  
|++|단항|  
|,|이항|  
|-|단항 및 이항|  
|--|단항|  
|->|단항|  
|/|이항|  
|<|이항|  
|<<|이항|  
|\<=|이항|  
|=|이항|  
|==|이항|  
|>|이항|  
|>=|이항|  
|>>|이항|  
|^|이항|  
|False|단항|  
|true|단항|  
|&#124;|이항|  
|&#124;&#124;|이항|  
|~|단항|  
  
## <a name="example"></a>예  
  
```cpp  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
```Output  
-5  
-4  
-3  
-2  
-1  
-2  
-3  
```  
  
## <a name="example"></a>예  
 다음 샘플을 사용할 때만 사용할 수 있는 연산자 통합 **/clr** 컴파일할 수 있습니다. 연산자를 통합 이항 연산자의 할당 양식을 만들고, 한 경우 정의 되지 않은 할당 연산자의 왼쪽에는 CLR 형식이 합니다.  
  
```cpp  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
```Output  
30  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)