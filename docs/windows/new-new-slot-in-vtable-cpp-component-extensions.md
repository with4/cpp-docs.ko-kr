---
title: 새 (새 vtable의 슬롯) (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32452b4fd44aed2bc399165b3184d974f22d90b6
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607013"
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>new(vtable의 새 슬롯)(C++ 구성 요소 확장)
합니다 **새** 키워드를 가상 멤버가 vtable의 new 슬롯을 얻게 되며 나타냅니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 Windows 런타임에서 지원 되지 않습니다.  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
### <a name="remarks"></a>설명  
  
 에 `/clr` 컴파일 **새** 가상 멤버가 vtable의 new 슬롯을 얻게 되며, 함수가 기본 클래스 메서드를 재정의 하지 않습니다 나타냅니다.  
  
 **새** 함수에 대 한 IL에 추가할 새 슬롯 한정자를 사용 하면 됩니다.  새 슬롯에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [MethodInfo.GetBaseDefinition 메서드](https://msdn.microsoft.com/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [메서드에 열거형](https://msdn.microsoft.com/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 다음 샘플의 결과 보여 줍니다 **새**합니다.  
  
```cpp  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **출력**  
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)