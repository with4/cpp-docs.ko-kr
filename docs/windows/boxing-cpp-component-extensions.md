---
title: Boxing (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- boxing, Visual C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05a0d83de045ed29b20ff14acc7fc81fb684a93e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650624"
---
# <a name="boxing--c-component-extensions"></a>Boxing(C++ 구성 요소 확장)
Visual c + + 컴파일러 라는 프로세스에서 개체 값 형식을 변환할 수 *boxing*, 및 개체 값의에서 형식으로 변환 이라는 프로세스 *unboxing*합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 C + + /cli CX 값 형식을 boxing 및 unboxing 참조 형식에 대 한 간단한 구문을 지원 합니다. 값 형식은 형식 `Object`의 변수에 할당될 때 boxing됩니다. `Object` 변수는 값 형식 변수에 할당되고 unboxing된 형식이 괄호 안에 지정될 때, 즉 개체 변수가 값 형식으로 캐스팅될 때 unboxing됩니다.  
  
```cpp  
  Platform::Object^  
  object_variable  = value_variable;  
value_variable = (value_type) object_variable;  
```  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
### <a name="examples"></a>예  
 다음 코드 예제에서는 `DateTime` 값을 boxing 및 unboxing합니다. 먼저,이 예제에서는 가져온를 `DateTime` 할당을 현재 날짜 및 시간을 나타내는 값을 `DateTime` 변수입니다. 그런 다음 `DateTime` 할당 하 여 boxed는 `Object` 변수입니다. Boxed 값을 다른 할당 하 여 unboxed가 마지막으로, `DateTime` 변수입니다.  
  
 예제 테스트를 만들려면를 `BlankApplication` 프로젝트를 대체 합니다 `BlankPage::OnNavigatedTo()` 메서드를 하 고 닫는 괄호 및 변수에 할당에 중단점을 지정 합니다 `str1`합니다. 이 예제에서는 닫는 대괄호에 도달 하면 검사 `str1`합니다.  
  
```cpp  
void BlankPage::OnNavigatedTo(NavigationEventArgs^ e)  
{  
    using namespace Windows::Globalization::DateTimeFormatting;  
  
    Windows::Foundation::DateTime dt, dtAnother;  
    Platform::Object^ obj1;  
  
    Windows::Globalization::Calendar^ c =   
        ref new Windows::Globalization::Calendar;  
    c->SetToNow();  
    dt = c->GetDateTime();  
    auto dtf = ref new DateTimeFormatter(  
                           YearFormat::Full,   
                           MonthFormat::Numeric,   
                           DayFormat::Default,   
                           DayOfWeekFormat::None);  
    String^ str1 = dtf->Format(dt);  
    OutputDebugString(str1->Data());  
    OutputDebugString(L"\r\n");  
  
    // Box the value type and assign to a reference type.  
    obj1 = dt;  
    // Unbox the reference type and assign to a value type.  
    dtAnother = (Windows::Foundation::DateTime) obj1;  
  
    // Format the DateTime for display.  
    String^ str2 = dtf->Format(dtAnother);  
    OutputDebugString(str2->Data());  
}  
```  
  
 자세한 내용은 [Boxing (C + + /cli CX)](http://msdn.microsoft.com/library/windows/apps/hh969554.aspx)합니다.  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 Visual C++ 컴파일러에서는 값 형식을 <xref:System.Object>로 boxing합니다. 값 형식을 <xref:System.Object>로 변환하는 컴파일러에서 정의된 변환 때문에 이 작업이 가능합니다.  
  
 Boxing 및 unboxing을 통해 값 형식으로 개체로 처리할 수 있습니다. 구조체 형식 및 int와 같은 기본 제공 형식을 비롯하여 값 형식을 <xref:System.Object> 형식으로 변환하거나 그 반대로 변환할 수 있습니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)  
  
-   [방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)  
  
-   [방법: Unbox](../dotnet/how-to-unbox.md)  
  
-   [표준 변환 및 암시적 boxing](../dotnet/standard-conversions-and-implicit-boxing.md)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 다음 예제에서는 암시적 boxing의 작동 방식을 보여 줍니다.  
  
```cpp  
// vcmcppv2_explicit_boxing2.cpp  
// compile with: /clr  
using namespace System;  
  
ref class A {  
public:  
   void func(System::Object^ o){Console::WriteLine("in A");}  
};  
  
value class V {};  
  
interface struct IFace {  
   void func();  
};  
  
value class V1 : public IFace {  
public:  
   virtual void func() {  
      Console::WriteLine("Interface function");  
   }  
};  
  
value struct V2 {  
   // conversion operator to System::Object  
   static operator System::Object^(V2 v2) {  
      Console::WriteLine("operator System::Object^");  
      return (V2^)v2;  
   }  
};  
  
void func1(System::Object^){Console::WriteLine("in void func1(System::Object^)");}  
void func1(V2^){Console::WriteLine("in func1(V2^)");}  
  
void func2(System::ValueType^){Console::WriteLine("in func2(System::ValueType^)");}  
void func2(System::Object^){Console::WriteLine("in func2(System::Object^)");}  
  
int main() {  
   // example 1 simple implicit boxing  
   Int32^ bi = 1;  
   Console::WriteLine(bi);  
  
   // example 2 calling a member with implicit boxing  
   Int32 n = 10;  
   Console::WriteLine("xx = {0}", n.ToString());  
  
   // example 3 implicit boxing for function calls  
   A^ a = gcnew A;  
   a->func(n);  
  
   // example 4 implicit boxing for WriteLine function call  
   V v;  
   Console::WriteLine("Class {0} passed using implicit boxing", v);  
   Console::WriteLine("Class {0} passed with forced boxing", (V^)(v));   // force boxing  
  
   // example 5 casting to a base with implicit boxing  
   V1 v1;  
   IFace ^ iface = v1;  
   iface->func();  
  
   // example 6 user-defined conversion preferred over implicit boxing for function-call parameter matching  
   V2 v2;  
   func1(v2);   // user defined conversion from V2 to System::Object preferred over implicit boxing  
                // Will call void func1(System::Object^);  
  
   func2(v2);   // OK: Calls "static V2::operator System::Object^(V2 v2)"  
   func2((V2^)v2);   // Using explicit boxing: calls func2(System::ValueType^)  
}  
```  
  
```Output  
1  
  
xx = 10  
  
in A  
  
Class V passed using implicit boxing  
  
Class V passed with forced boxing  
  
Interface function  
  
in func1(V2^)  
  
in func2(System::ValueType^)  
  
in func2(System::ValueType^)  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)