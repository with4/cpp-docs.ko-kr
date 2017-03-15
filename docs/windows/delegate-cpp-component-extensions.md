---
title: "delegate(C++ 구성 요소 확장) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "delegate_cpp"
  - "delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delegate 키워드[C++]"
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delegate(C++ 구성 요소 확장)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수 포인터를 나타내는 형식을 선언합니다.  
  
## 모든 런타임  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]와 공용 언어 런타임 모두 대리자를 지원합니다.  
  
### 설명  
 `delegate`는 상황에 맞는 키워드입니다.  자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)을 참조하십시오.  
  
 컴파일 타임에 형식이 대리자인지 감지하려면 `__is_delegate()` 형식 특성을 사용합니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하십시오.  
  
## Windows 런타임\(Windows Runtime\)  
 C\+\+\/CX는 다음 구문을 사용하여 대리자를 지원합니다.  
  
### 구문  
  
```cpp  
  
access delegate return-type delegate-type-identifier ([ parameters ])  
```  
  
### 매개 변수  
 *access*  
 \(선택 사항\) `public`\(기본값\) 또는 `private`일 수 있는 대리자의 내게 필요한 옵션입니다.  함수 프로토타입은 `const` 또는 `volatile` 키워드로 정규화할 수도 있습니다.  
  
 *return\-type*  
 함수 프로토타입의 반환 형식입니다.  
  
 *delegate\-type\-identifier*  
 선언된 대리자 형식의 이름입니다.  
  
 *parameters*  
 \(선택 사항\) 함수 프로토타입의 형식과 식별자입니다.  
  
### 설명  
 *delegate\-type\-identifier* 를 사용하여 동일한 프로토타입을 가진 이벤트를 대리자로 선언합니다.  자세한 내용은 [대리자\(C\+\+\/CX\)](../Topic/Delegates%20\(C++-CX\).md)를 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 공용 언어 런타임에서는 다음 구문을 사용하여 대리자를 지원합니다.  
  
### 구문  
  
```cpp  
  
access delegate function_declaration  
```  
  
### 매개 변수  
 *access*  
 \(선택 사항\) 어셈블리 외부의 대리자 액세스 가능성은 공용 또는 전용이 될 수 있습니다.  기본값은 private입니다.  클래스 내에서 대리자는 내게 필요한 옵션을 가질 수 있습니다.  
  
 *function\_declaration*  
 대리자에 바인딩할 수 있는 함수의 시그니처입니다.  대리자의 반환 형식은 관리되는 형식이 될 수 있습니다.  상호 운용성을 위해 대리자의 반환 형식이 CLS 형식이 되도록 하는 것이 좋습니다.  
  
 바인딩되지 않은 대리자를 정의하려면  *function\_declaration* 의 첫 번째 매개 변수는 개체에 대한 `this` 포인터의 형식이 되어야 합니다.  자세한 내용은 [바인딩되지 않은 대리자](../misc/unbound-delegates.md)을 참조하십시오.  
  
### 설명  
 대리자는 멀티 캐스트입니다. "함수 포인터"는 관리되는 클래스 내의 하나 이상의 메서드에 바인딩될 수 있습니다.  **delegate** 키워드는 특정 메서드 서명을 사용하여 멀티캐스트 대리자 형식을 정의합니다.  
  
 대리자는 정적 메서드와 같이 값 클래스의 메서드에 바인딩할 수도 있습니다.  
  
 대리자에는 다음과 같은 특징이 있습니다.  
  
-   이는 **System::MulticastDelegate**에서 상속합니다.  
  
-   관리되는 클래스에 대한 포인터 또는 **NULL**\(정적 메서드에 바인딩하는 경우\) 및 지정된 형식의 정규화된 메서드 등 두 가지 인수를 취하는 생성자가 있습니다.  
  
-   `Invoke`라는 메서드가 있으며, 서명이 대리자의 선언된 서명과 일치합니다.  
  
 대리자가 호출되면 해당 함수는 연결된 순서대로 호출됩니다.  
  
 대리자의 반환 값은 마지막으로 연결된 멤버 함수에서 반환된 값입니다.  
  
 대리자를 오버로드할 수 없습니다.  
  
 대리자는 바운드 또는 언바운드일 수 있습니다.  
  
 바인딩된 대리자를 인스턴스화할 때 첫 번째 인수는 개체 참조가 되어야 합니다.  대리자 인스턴스화의 두 번째 인수는 관리되는 클래스 개체의 메서드 주소 또는 값 형식의 메서드에 대한 포인터여야 합니다.   대리자 인스턴스화의 두 번째 인수는 전체 클래스 범위 구문으로 메서드 이름을 지정하고 주소 연산자를 적용해야 합니다.  
  
 바인딩되지 않은 대리자를 인스턴스화하면 첫 번째 인수는 관리되는 클래스 개체의 메서드 주소 또는 값 형식의 메서드에 대한 포인터여야 합니다.   인수는 전체 클래스 범위 구문으로 메서드 이름을 지정하고 주소 연산자를 적용해야 합니다.  
  
 정적 또는 전역 함수에 대한 대리자를 만들면 매개 변수 함수\(선택 사항으로 함수의 주소\) 하나만 필요합니다.  
  
 대리자에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [바인딩되지 않은 대리자](../misc/unbound-delegates.md)  
  
-   [방법: 대리자 정의 및 사용](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [값 클래스의 멤버에 대한 대리자](../misc/how-to-associate-delegates-to-members-of-a-value-class.md)  
  
-   [관리되지 않는 함수에 대한 대리자](../misc/how-to-associate-delegates-to-unmanaged-functions.md)  
  
-   [구성된 대리자](../misc/how-to-compose-delegates.md)  
  
-   [방법: 함수 포인터가 필요한 네이티브 함수에 대리자 전달](../misc/how-to-pass-a-delegate-hat-to-a-native-function-expecting-a-function-pointer.md)  
  
-   [Generic Delegates \(Visual C\+\+\)](../windows/generic-delegates-visual-cpp.md)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 예제에서는 대리자를 선언, 초기화 및 호출하는 방법을 보여 줍니다.  
  
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
  
 **Output**  
  
  **in func1 8**  
 **in func1 9**  
 **in func2 9**  
 **in func2 10**  
 **in static func3 11**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)