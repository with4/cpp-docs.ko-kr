---
title: "sealed (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sealed_cpp
- sealed
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb8a8b7ea695d878235898a8741adf04ba91748c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="sealed--c-component-extensions"></a>sealed(C++ 구성 요소 확장)
`sealed`는 가상 멤버를 재정의할 수 없거나 형식을 기본 형식으로 사용할 수 없음을 나타내는 ref 클래스에 대한 상황에 맞는 키워드입니다.  
  
> [!NOTE]
>  ISO C + + 11 표준 언어에는 [최종](../cpp/final-specifier.md) Visual Studio에서 지원 되는 키워드입니다. 표준 클래스에서는 `final`을 사용하고 ref 클래스에서는 `sealed`를 사용합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
  
## <a name="syntax"></a>구문
  
```  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
```  
  
### <a name="parameters"></a>매개 변수  
  
 *identifier*  
 함수나 클래스의 이름입니다.  
  
 *반환 형식*  
 함수에서 반환하는 형식입니다.  
  
## <a name="remarks"></a>설명  
  
 첫 번째 구문 예에서는 클래스가 봉인되어 있고, 두 번째 예에서는 가상 함수가 봉인되어 있습니다.  
  
 `sealed` 키워드는 네이티브 대상에 대 한 Windows 런타임 및 공용 언어 런타임 (CLR)에 대 한 사용할 수 있습니다. 자세한 내용은 참조 [재정의 지정자 및 네이티브 컴파일](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)합니다.  
  
 사용 하 여 형식이 봉인 되어 있는지 여부를 컴파일 타임에 감지할 수는 `__is_sealed(type)` 형식 특성입니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
 `sealed`는 상황에 맞는 키워드입니다.  자세한 내용은 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 참조 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 (이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 다음 코드 예제에서는 가상 멤버에 대한 `sealed`의 영향을 보여 줍니다.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
```Output  
X::f override of I1::f  
X::f override of I1::g  
Y::f override of I1::f  
```  
  
 다음 코드 예제에서는 클래스를 sealed로 표시하는 방법을 보여 줍니다.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)