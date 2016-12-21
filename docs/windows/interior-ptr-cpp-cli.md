---
title: "interior_ptr (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "stdcli::language::interior_ptr"
  - "interior_ptr_cpp"
  - "interior_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interior_ptr keyword [C++]"
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interior_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*내부 포인터*는  개체 자체가 아니라 참조 형식 내부에 포인터를 선언합니다.  내부 포인터 참조 핸들을 값 형식, boxed 형식 핸들, 관리 되는 형식의 멤버 또는 관리 되는 배열의 요소를 가리킬 수 있습니다.  
  
## 모든 런타임  
 \(모든 런타임에 적용되는 이 언어 기능에 대한 설명이 없습니다.\)  
  
## Windows 런타임\(Windows Runtime\)  
 \(이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 다음 구문 예제는 내부 포인터입니다.  
  
### 구문  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### 매개 변수  
 *cv\_qualifier*  
 **const** 또는  `volatile`  한정자입니다.  
  
 *type*  
 *initializer*의 형식입니다.  
  
 *var*  
 `interior_ptr` 변수의 이름입니다.  
  
 *initializer*  
 구성원 참조 형식, 관리 되는 배열 또는 네이티브 포인터에 할당할 수 있는 모든 개체 요소입니다.  
  
### 설명  
 네이티브 포인터는 개체의 인스턴스를 이동시키는 가비지 수집기로부터 도출되는 관리된 힙에 위치 변경의 항목을 추적할 수 없습니다.  잘못 된 인스턴스를 참조 하는 포인터를 런타임에 새로 위치가 지정 된 개체에 포인터를 업데이트 해야 합니다.  
  
 `interior_ptr` 는 네이티브 포인터의 기능에 상위 집합을 나타냅니다.  따라서 네이티브 포인터에 할당할 수 있는 모든 것은  `interior_ptr` 에 할당될 수 있습니다.  내부 포인터는 네이티브 포인터, 포인터 산술 및 비교를 포함하여 동일한 일련의 작업을 수행할 수 있습니다.  
  
 내부 포인터로 스택에 선언할 수 있습니다.  내부 포인터를 클래스 멤버로 선언할 수 없습니다.  
  
 내부 포인터가 스택에 존재하므로 내부 포인터 주소는 관리되지 않는 포인터를 생성합니다.  
  
 `interior_ptr`는 암시적으로 변환 된  `bool` 를 가지고 있어 조건문에 사용할 수 있습니다.  
  
 가비지 수집 된 힙에 이동할 수 없는 개체를 가리키는 내부 포인터를 선언 하는 방법에 대한 정보를 보려면  [pin\_ptr](../windows/pin-ptr-cpp-cli.md)을 참조하십시오.  
  
 `interior_ptr`는 cli 네임스페이스에 있습니다.  자세한 내용은 [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)를 참조하십시오.  
  
 내부 포인터에 대한 자세한 내용을 참고하십시오.  
  
-   [How to: Declare and Use Interior Pointers and Managed Arrays \(C\+\+\/CLI\)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [How to: Declare Value Types with the interior\_ptr Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [How to: Overload Functions with Interior Pointers and Native Pointers \(C\+\+\/CLI\)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [How to: Declare Interior Pointers with the const Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 샘플에 내부 포인터를 사용 여 참조 형식으로 선언하는 방법을 보여줍니다.  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **Output**  
  
 **1**   
**2**   
**3**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)