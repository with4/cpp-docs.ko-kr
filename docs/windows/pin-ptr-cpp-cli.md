---
title: "pin_ptr (C++/CLI) | Microsoft Docs"
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
  - "pin_ptr_cpp"
  - "stdcli::language::pin_ptr"
  - "pin_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pinning pointers"
  - "pin_ptr keyword [C++]"
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
caps.latest.revision: 28
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pin_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

공용 언어 런타임만을 사용하는 *고정 포인터*를 선언합니다.  
  
## 모든 런타임  
 \(모든 런타임에 적용되는 이 언어 기능에 대한 설명이 없습니다.\)  
  
## Windows 런타임\(Windows Runtime\)  
 \(이 언어 기능은 Windows 런타임에서 지원되지 않습니다.\)  
  
## 공용 언어 런타임  
 *고정 포인터*는 가비지 수집된 힙에 이동하는 것을 가리키는 개체를 방지하는 내부포인터입니다.  즉, 공용 언어 런타임에서 고정 포인터의 값은 변경되지 않습니다.  주소가 관리되지 않는 함수 호출을 확인 중에 예기치 않게 변경되지 않도록 관리되지 않는 함수에 관리되는 클래스의 주소를 전달할 때 필요합니다.  
  
### 구문  
  
```cpp  
[cli::]pin_ptr<cv_qualifier type> var = &initializer;  
```  
  
### 매개 변수  
 *cv\_qualifier*  
 `const`또는  `volatile`  한정자입니다.  고정 포인터는 기본적으로  `volatile` 입니다.  그것은 중복하지만  `volatile`  고정 포인터를 선언 오류를 발생시키지 않습니다.  
  
 *type*  
 `initializer`의 형식입니다.  
  
 *var*  
 `pin_ptr` 변수의 이름입니다.  
  
 *initializer*  
 구성원 참조 형식, 관리 되는 배열 또는 네이티브 포인터에 할당할 수 있는 모든 개체 요소입니다.  
  
### 설명  
 `pin_ptr` 는 네이티브 포인터의 기능에 상위 집합을 나타냅니다.  따라서 네이티브 포인터에 할당할 수 있는 모든 것은  `pin_ptr` 에 할당될 수 있습니다.  내부 포인터는 네이티브 포인터, 포인터 산술 및 비교를 포함하여 동일한 일련의 작업을 수행할 수 있습니다.  
  
 관리되는 클래스의 개체 또는 하위 개체는 고정될 수 있습니다. 그 경우 공용 언어 런타임은 가비지 수집 중에 이동하지 않습니다.  주 사용은 포인터 관리 되는 데이터를 관리되지 않는 함수 호출의 실제 매개변수로 전달하는 것입니다.  수집주기 동안 런타임은 고정 포인터에 대해 생성 된 메타 데이터를 검열하고 그것을 가리키는 항목을 이동하지 않습니다.  
  
 개체를 고정하면 그 값 필드를 고정합니다; 즉, 기본 또는 값 형식의 필드입니다.  그러나 핸들을 추적하여 \(`%`\) 선언된 필드는 고정되지 않습니다.  
  
 관리되는 개체에 정의 된 하위 개체를 고정하면 전체 개체를 고정하는 효과가 있습니다.  
  
 고정 포인터가 새 값을 가리 키도록 재 할당하는 경우, 이전 인스턴스가 더 이상 고정된 것으로 간주됩니다.  
  
 `pin_ptr` 가 가르킬 때 개체가 고정됩니다.  이 개체의 고정 포인터가 범위를 벗어나면 더 이상 고정되지 않거나  [nullptr](../windows/nullptr-cpp-component-extensions.md)로 설정됩니다.   `pin_ptr` 가 범위를 벗어나면 고정된 개체가 가비지 수집기로 힙에서 이동할 수 있습니다.  여전히 개체를 가리 네이티브 포인터가 업데이트되지 않으며, 참조 중 하나는 복구 할 수없는 예외를 발생시킬 수 있습니다.  
  
 고정 포인터가 개체를 포인트하지 않는 경우\(모든 고정 포인터는 범위에서 나가서 다른 객체를 가리키도록 재 할당되거나 또는 [nullptr](../windows/nullptr-cpp-component-extensions.md)에 할당됩니다\), 개체는 고정되지 않습니다.  
  
 고정 포인터 참조 핸들을 값 형식, boxed 형식 핸들 또는 관리되는 형식의 멤버 또는 관리되는 배열의 요소를 가리킬 수 있습니다.  참조 형식을 가리킬 수 없습니다.  
  
 네이티브 개체를 가리키는  `pin_ptr` 주소를 사용하면 정의되지 않은 동작을 발생시킵니다.  
  
 고정 포인터는 스택에 정적이 아닌 지역 변수로 선언할 수 있습니다.  
  
 다음과 같이 고정 포인터를 사용할 수 없습니다.  
  
-   함수 매개 변수  
  
-   함수의 반환 형식  
  
-   클래스의 멤버  
  
-   캐스트의 타겟 형식  
  
 `pin_ptr`은 `cli` 네임스페이스입니다.  자세한 내용은 [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)을 참조하십시오.  
  
 내부 포인터에 대한 자세한 내용은 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)를 참조하십시오.  
  
 고정 포인터에 대한 자세한 내용은 [How to: Pin Pointers and Arrays](../windows/how-to-pin-pointers-and-arrays.md) 및 [How to: Declare Pinning Pointers and Value Types](../windows/how-to-declare-pinning-pointers-and-value-types.md)를 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 예제에서는  `pin_ptr` 을 사용하여 배열의 첫 번째 요소 위치를 제한할 수 있습니다.  
  
```  
// pin_ptr_1.cpp  
// compile with: /clr   
using namespace System;  
#define SIZE 10  
  
#pragma unmanaged  
// native function that initializes an array  
void native_function(int* p) {  
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;  
}  
#pragma managed  
  
public ref class A {  
private:  
   array<int>^ arr;   // CLR integer array  
  
public:  
   A() {  
      arr = gcnew array<int>(SIZE);  
   }  
  
   void load() {  
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr  
   int* np = p;   // pointer to the first element in arr  
   native_function(np);   // pass pointer to native function  
   }  
  
   int sum() {  
      int total = 0;  
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];  
      return total;  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   a->load();   // initialize managed array using the native function  
   Console::WriteLine(a->sum());  
}  
```  
  
 **Output**  
  
  **45** **예제**  
  
 다음 예제에서는 내부 포인터, 고정 포인터를 변환할 수 있고 및 주소 연산자\(`&`\) 주소의 반환 형식이 피연산자가 관리 되는 힙에 있을 때 내부포인터인 것을 보여줍니다.  
  
```  
// pin_ptr_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   G() : i(1) {}  
   int i;  
};  
  
ref struct H {  
   H() : j(2) {}  
   int j;  
};  
  
int main() {  
   G ^ g = gcnew G;   // g is a whole reference object pointer  
   H ^ h = gcnew H;  
  
   interior_ptr<int> l = &(g->i);   // l is interior pointer  
  
   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer  
  
   k = l;   // ok  
   Console::WriteLine(*k);  
};  
```  
  
 **Output**  
  
 **1** **예제**  
  
 다음 예제에서는 고정 포인터를 다른 형식으로 캐스팅 될 수 있음을 보여줍니다.  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr< int > pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **Output**  
  
 **8**   
**255**