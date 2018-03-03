---
title: "대리자 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- delegate_cpp
- delegate
dev_langs:
- C++
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30fd64fd37fb30c34b5d4f5901f16143fb1cd701
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="delegate--c-component-extensions"></a>delegate(C++ 구성 요소 확장)
함수 포인터를 나타내는 형식을 선언 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 Windows 런타임 및 공용 언어 런타임 대리자를 지원 합니다.  
  
### <a name="remarks"></a>설명  
 `delegate`는 상황에 맞는 키워드입니다. 자세한 내용은 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)합니다.  
  
 컴파일 타임에 대리자 형식이 경우를 검색 하려면 사용 된 `__is_delegate()` 형식 특성입니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 C + + /cli CX 다음 구문 사용 하 여 대리자를 지원 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
access  
delegate  
return-type  
delegate-type-identifier  
(  
[ parameters ]  
)  
  
```  
  
### <a name="parameters"></a>매개 변수  
 *access*  
 (선택 사항) 될 수 있는 대리자의 내게 필요한 옵션 `public` (기본값) 또는 `private`합니다. 함수 프로토타입 한정 될 수도 수 있습니다는 `const` 또는 `volatile` 키워드입니다.  
  
 *반환 형식*  
 함수 프로토타입의 반환 형식입니다.  
  
 *대리자 형식 식별자*  
 선언 된 대리자 형식의 이름입니다.  
  
 *매개 변수*  
 (선택 사항) 형식 및 함수 프로토타입의 식별자입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 *대리자 형식 식별자* 대리자와 동일한 프로토타입 사용 하 여 이벤트를 선언할 수 있습니다. 자세한 내용은 참조 [대리자 (C + + /cli CX)](../cppcx/delegates-c-cx.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 공용 언어 런타임에서 다음 구문 사용 하 여 대리자를 지원 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
access  
delegate  
function_declaration  
  
```  
  
### <a name="parameters"></a>매개 변수  
 *access*  
 (선택 사항) 대리자는 어셈블리 외부에서 액세스 가능성은 public 또는 private 수 있습니다.  기본값은 private입니다.  클래스, 대리자는 접근성을 가질 수 있습니다.  
  
 *function_declaration*  
 대리자에 바인딩될 수 있는 함수의 서명입니다. 대리자의 반환 형식에는 관리 되는 형식일 수 있습니다. 상호 운용성을 위해 대리자의 반환 형식은 CLS 형식일 것이 좋습니다.  
  
 바인딩되지 않은 대리자에서 첫 번째 매개 변수를 정의 하려면 *function_declaration* 의 유형 이어야 합니다는 `this` 개체에 대 한 포인터입니다. 
  
### <a name="remarks"></a>설명  
 대리자는 멀티 캐스트: "함수 포인터" 관리 되는 클래스 내에서 하나 이상의 메서드에 바인딩할 수 있습니다. **위임** 키워드 특정 메서드 서명 사용 하 여 멀티 캐스트 대리자 형식을 정의 합니다.  
  
 대리자 정적 메서드와 같은 값 클래스의 메서드에 바인딩될 수도 있습니다.  
  
 대리자에는 다음과 같은 특징이 있습니다.  
  
-   상속 된 **system:: multicastdelegate**합니다.  
  
-   두 개의 인수를 사용 하는 생성자가: 관리 되는 클래스에 대 한 포인터 또는 **NULL** (정적 메서드에 바인딩하)는 경우 지정 된 형식의 정규화 된 메서드 및 합니다.  
  
-   `Invoke`라는 메서드가 있으며, 서명이 대리자의 선언된 서명과 일치합니다.  
  
 대리자를 호출 하면 해당 함수는 연결 된 순서 대로 호출 됩니다.  
  
 대리자의 반환 값은 집합의 마지막 연결 된 멤버 함수에서 반환 값입니다.  
  
 대리자를 오버 로드할 수 없습니다.  
  
 대리자는 바인딩 또는 바인딩 해제 수 있습니다.  
  
 바운드 대리자를 인스턴스화할 때 첫 번째 인수는 개체 참조 이어야 합니다.  대리자 인스턴스화가의 두 번째 인수는 값 형식의 메서드에 대 한 포인터는 관리 되는 클래스 개체의 메서드나 클래스의 주소가 될 중 하나입니다.   대리자 인스턴스화가의 두 번째 인수는 전체 클래스 범위 구문 사용 하 여 메서드 이름을 지정 하 고 address-of 연산자를 적용 해야 합니다.  
  
 바인딩되지 않은 대리자를 인스턴스화할 때 첫 번째 인수는 메서드는 관리 되는 클래스 개체 또는 값 형식의 메서드에 대 한 포인터의 주소 이어야 합니다.   인수는 전체 클래스 범위 구문 사용 하 여 메서드 이름을 지정 하 고 address-of 연산자를 적용 해야 합니다.  
  
 하나의 매개 변수는 필수 전역 또는 정적 함수에 대리자를 만들 때: 함수 (필요에 따라 함수의 주소).  
  
 대리자에 대 한 자세한 내용은 참조 하세요.  
  
-   [방법: 대리자 정의 및 사용(C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [제네릭 대리자(Visual C++)](../windows/generic-delegates-visual-cpp.md)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 선언, 초기화 및 대리자를 호출 하는 방법을 보여 줍니다.  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **출력**  
  
```Output  
in func1 8  
  
in func1 9  
  
in func2 9  
  
in func2 10  
  
in static func3 11  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)