---
title: pin_ptr (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afc99a352e0bde7918cab460293ff23061377551
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="pinptr-ccli"></a>pin_ptr(C++/CLI)
선언는 *고정 포인터*, 공용 언어 런타임만을 사용 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 (이 언어 기능은 Windows 런타임에서 지원 되지 않습니다.)  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 A *고정 포인터* 개체를 방지 하는 내부 포인터를 가리키고 가비지 수집 힙에 이동 합니다. 즉, 고정 포인터의 값은 공용 언어 런타임에 의해 변경 되지 않습니다. 이 주소는 관리 되지 않는 함수 호출을 확인 하는 동안 예기치 않게 변경 되지 않도록 관리 되지 않는 함수에 관리 되는 클래스의 주소를 전달 하는 경우에 필요 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>매개 변수  
 *cv_qualifier*  
 `const` 또는 `volatile` 한정자입니다. 기본적으로 고정 포인터는 `volatile`합니다. 고정 포인터를 선언 하는 오류가 아니라 하지만 중복 `volatile`합니다.  
  
 *type*  
 `initializer`의 형식입니다.  
  
 *var*  
 `pin_ptr` 변수의 이름입니다.  
  
 *initializer*  
 참조 형식의 멤버, 관리되는 배열의 요소 또는 네이티브 포인터에 할당할 수 있는 다른 모든 개체입니다.  
  
### <a name="remarks"></a>설명  
 A `pin_ptr` 네이티브 포인터 기능의 상위 집합을 나타냅니다. 따라서 네이티브 포인터에 할당할 수 있는 모든 항목 또한에 지정할 수는 `pin_ptr`합니다. 내부 포인터는 네이티브 포인터로서 비교 및 포인터 산술을 포함한 동일한 일련의 작업을 수행할 수 있습니다.  
  
 관리 되는 클래스의 하위 개체 또는 고정할 수 있습니다,이 경우 공용 언어 런타임 이동 하지 것입니다 가비지 수집 중입니다. 이 주 용도 관리 되지 않는 함수 호출의 실제 매개 변수로 관리 되는 데이터에 대 한 포인터를 전달 하는 것입니다. 컬렉션 주기 동안 런타임에서 만든 고정 포인터에 대 한 메타 데이터를 검사 하 및를 가리키는 항목을 이동 하지 않습니다.  
  
 값 필드를 고정 하는 또한 개체를 고정 즉, 기본 형식의 필드 또는 값 입력 합니다. 그러나 핸들을 추적 하 여 선언 된 필드 (`%`) 고정 되지 됩니다.  
  
 관리 되는 개체에 정의 된 하위 개체를 고정 전체 개체 고정은 효과가 없습니다.  
  
 고정 포인터를 새 값을 가리키도록 다시 할당 하면 이전 인스턴스를 더 이상 것으로 간주 됩니다 고정 합니다.  
  
 개체 고정 된 동안에는 `pin_ptr` 것을 가리킵니다. 해당 고정 포인터가 범위를 벗어나거나 또는로 설정 된 경우 개체가 더 이상 고정 [nullptr](../windows/nullptr-cpp-component-extensions.md)합니다. 이후에 `pin_ptr` 가비지 수집기에서 고정 된 개체 범위를 벗어난 힙에서 이동할 수 있습니다. 여전히 개체를 가리키는 모든 네이티브 포인터, 업데이트 되지 않습니다 및 그 중 하나를 참조 해제 복구할 수 없는 예외가 발생 시킬 수 있습니다.  
  
 없는 고정 포인터는 개체를 가리킬 경우 (모든 고정 포인터가 범위에서 오류가 발생 했습니다.은 다른 개체를 가리키도록 다시 할당 또는 할당 된 [nullptr](../windows/nullptr-cpp-component-extensions.md)), 개체 고정 하는 수 없도록 보장 합니다.  
  
 고정 포인터는 참조 핸들, 값 형식 또는 boxed 형식 핸들, 관리 되는 형식의 멤버 또는 관리 되는 배열의 요소를 가리킬 수 있습니다. 참조 형식 가리킬 수 없습니다.  
  
 주소는 `pin_ptr` 포인트 네이티브 개체에 정의 되지 않은 동작이 발생 하 합니다.  
  
 만 고정 포인터는 스택에 비정적 지역 변수로 선언할 수 있습니다.  
  
 으로 고정 포인터를 사용할 수 없습니다.  
  
-   함수 매개 변수  
  
-   함수의 반환 형식  
  
-   클래스의 멤버  
  
-   캐스트의 대상 형식입니다.  
  
 `pin_ptr` 에 `cli` 네임 스페이스입니다. 자세한 내용은 참조 [플랫폼, default 및 cli 네임 스페이스](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)합니다.  
  
 내부 포인터에 대 한 자세한 내용은 참조 [interior_ptr (C + + /cli CLI)](../windows/interior-ptr-cpp-cli.md)합니다.  
  
 포인터 고정 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 고정 포인터 및 배열](../windows/how-to-pin-pointers-and-arrays.md) 및 [하는 방법: 고정 포인터를 선언 및 값 형식](../windows/how-to-declare-pinning-pointers-and-value-types.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 `pin_ptr` 배열의 첫 번째 요소의 위치를 제한할 수 있습니다.  
  
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
  
 **출력**  
  
```Output  
45  
```  
  
 **예제**  
  
 다음 예제에서는 주소 연산자의 반환 형식 및 내부 포인터 고정 포인터가 변환 될 수 있음을 보여 줍니다 (`&`)는 피연산자가 관리 되는 힙에 내부 포인터입니다.  
  
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
  
 **출력**  
  
```Output  
1  
```  
  
 **예제**  
  
 다음 예제 하는 고정 포인터를 다른 형식으로 캐스팅할 수 있습니다.  
  
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
   pin_ptr<int> pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **출력**  
  
```Output  
8  
255  
```