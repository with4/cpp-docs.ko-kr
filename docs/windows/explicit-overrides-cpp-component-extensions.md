---
title: "명시적 재정의 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 387141945882bf3c491c55a4a8ab8ab3804e876a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="explicit-overrides--c-component-extensions"></a>명시적 재정의(C++ 구성 요소 확장명)
이 항목에서는 기본 클래스 또는 인터페이스의 멤버를 명시적으로 재정의 하는 방법을 설명 합니다. 명명 된 명시적 재정의 다른 이름이 있는 파생 메서드로 메서드를 재정의 하만 사용 해야 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 **구문**  
  
```  
  
      overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **매개 변수**  
  
 *함수 재정의-선언*  
 재정의 함수의 반환 형식, 이름 및 인수 목록입니다.  참고는 재정의 함수를 재정의 하는 함수와 같은 이름을 사용할 필요가 없습니다.  
  
 *type*  
 재정의 하는 함수를 포함 하는 기본 형식입니다.  
  
 *function*  
 재정의 하려면 하나 이상의 함수 이름의 쉼표로 구분 된 목록.  
  
 *함수 재정의-정의*  
 재정의 함수를 정의 하는 함수 본문 문입니다.  
  
 **주의**  
  
 사용 하 여 명시적 메서드 서명에 대 한 별칭을 만들려면 또는 메서드에 동일한 서명이 witht에 대 한 다른 구현을 제공 하기를 재정의 합니다.  
  
 상속 된 형식과 상속 된 형식 멤버의 동작을 수정 하는 방법에 대 한 정보를 참조 하십시오. [재정의 지정자](../windows/override-specifiers-cpp-component-extensions.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 네이티브 코드에서 명시적에 대 한 정보를 재정의 하거나로 컴파일된 코드 **/clr:oldSyntax**, 참조 [명시적으로 재정의](../cpp/explicit-overrides-cpp.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 간단 하 고 암시적 override 및 멤버의 구현을 기본 인터페이스에서 명시적으로 재정의 사용 하지  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **출력**  
  
```Output  
X::f override of I1::f  
```  
  
 **예제**  
  
 다음 코드 예제에서는 모든 인터페이스 멤버 일반적인 서명 사용 하 여 명시적 재정의 구문은 사용 하 여 구현 하는 방법을 보여 줍니다.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **출력**  
  
```Output  
X::f override of I1::f and I2::f  
X::f override of I1::f and I2::f  
```  
  
 **예제**  
  
 다음 코드 예제에서는 방식 함수 재정의 구현 하는 함수에서 다른 이름으로 사용할 수를 보여 줍니다.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **출력**  
  
```Output  
X::g  
```  
  
 **예제**  
  
 다음 코드 예제에서는 형식 안전 컬렉션을 구현 하는 명시적 인터페이스 구현을 보여 줍니다.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)