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
ms.openlocfilehash: a87dadfd4787e4bd0100efb8fe7ffe2b1e7a8899
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607854"
---
# <a name="pinptr-ccli"></a>pin_ptr(C++/CLI)
선언를 *대 한 고정 포인터*, 공용 언어 런타임만을 사용 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 (이 언어 기능 Windows 런타임에서 지원 되지 않습니다.)  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 A *대 한 고정 포인터* 개체를 방지 하는 내부 포인터로 가리키는 가비지 수집 힙에 이동 합니다. 즉, 공용 언어 런타임에서 고정 포인터의 값 변경 되지 않습니다. 주소는 관리 되지 않는 함수 호출의 해결 하는 동안 예기치 않게 변경 되지 것입니다 있도록 관리 되는 클래스의 주소는 관리 되지 않는 함수에 전달 하는 경우 이것이 필요 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>매개 변수  
 *cv_qualifier*  
 **const** 나 **volatile** 한정자입니다. 기본적으로 고정 포인터가 **volatile**합니다. 고정 포인터를 선언 하는 오류가 아니라 하지만 중복 될 **volatile**합니다.  
  
 *type*  
 유형의 *이니셜라이저*합니다.  
  
 *var*  
 이름을 합니다 **pin_ptr** 변수입니다.  
  
 *initializer*  
 참조 형식의 멤버, 관리되는 배열의 요소 또는 네이티브 포인터에 할당할 수 있는 다른 모든 개체입니다.  
  
### <a name="remarks"></a>설명  
 A **pin_ptr** 네이티브 포인터 기능의 상위 집합을 나타냅니다. 따라서 네이티브 포인터에 할당할 수 있는 것도 할당할 수는 **pin_ptr**합니다. 내부 포인터는 네이티브 포인터로서 비교 및 포인터 산술을 포함한 동일한 일련의 작업을 수행할 수 있습니다.  
  
 개체 또는 관리 되는 클래스의 하위 개체를 고정할 수 있습니다,이 경우 공용 언어 런타임 이동 하지 않음을 가비지 수집 중입니다. 이 보안 주체를 사용 하 여 관리 되지 않는 함수 호출의 실제 매개 변수로 관리 되는 데이터에 대 한 포인터를 전달 하는 것입니다. 수집 주기, 만든 고정 포인터에 대 한 메타 데이터를 검사 하는 런타임과 가리키는 항목을 이동 하지 않습니다.  
  
 해당 값 필드를 고정 하는 또한 개체를 고정 합니다. 즉, 기본 형식의 필드 또는 값 형식입니다. 필드 핸들을 추적 하 여 선언 하는 반면 (`%`) 고정 되지 됩니다.  
  
 관리 되는 개체에 정의 된 하위 개체를 고정 효과가 전체 개체를 고정 합니다.  
  
 고정 포인터를 새 값을 가리키도록 다시 할당를 가리키는 이전 인스턴스가 더 이상 것으로 간주 됩니다 고정 합니다.  
  
 개체는 고정 된 동안에을 **pin_ptr** 가리키는 합니다. 개체의 고정 포인터가 범위를 벗어날 또는로 설정 된 경우 고정 되어 있지 [nullptr](../windows/nullptr-cpp-component-extensions.md)합니다. 후 합니다 **pin_ptr** 고정 된 개체 범위를 벗어나면 가비지 수집기에 의해 힙에서 이동할 수 있습니다. 여전히 개체를 가리키는 모든 네이티브 포인터를 업데이트 되지 않습니다 하 고 그 중 하나를 참조 해제 복구할 수 없는 예외가 발생 시킬 수 있습니다.  
  
 없는 고정 포인터 개체를 가리키는 경우 (오류가 발생 했습니다. 범위를 벗어납니다,은 다른 개체를 가리키도록 다시 할당 또는 할당 된 모든 고정 포인터 [nullptr](../windows/nullptr-cpp-component-extensions.md)), 없습니다 고정 되도록 하는 개체는 항상 있습니다.  
  
 고정 포인터는 참조 핸들, 값 형식 또는 boxed 형식 핸들, 관리 되는 형식, 멤버 또는 관리 되는 배열의 요소를 가리킬 수 있습니다. 참조 형식으로 가리킬 수 없습니다.  
  
 주소를 **pin_ptr** 는 네이티브 개체를 가리키는 정의 되지 않은 동작을 유발 합니다.  
  
 만 고정 포인터는 스택에 static이 아니고 로컬 변수로 선언할 수 있습니다.  
  
 고정 포인터를 사용할 수 없습니다.  
  
-   함수 매개 변수  
  
-   함수의 반환 형식  
  
-   클래스의 멤버  
  
-   캐스트의 대상 형식입니다.  
  
 **pin_ptr** 에 `cli` 네임 스페이스입니다. 자세한 내용은 [Platform, default 및 cli 네임 스페이스](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)합니다.  
  
 내부 포인터에 대 한 자세한 내용은 참조 하세요. [interior_ptr (C + + /cli CLI)](../windows/interior-ptr-cpp-cli.md)합니다.  
  
 고정 포인터에 대 한 자세한 내용은 참조 하세요. [방법: 고정 포인터 및 배열](../windows/how-to-pin-pointers-and-arrays.md) 및 [방법: 고정 포인터를 선언 하 고 값 형식](../windows/how-to-declare-pinning-pointers-and-value-types.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 다음 예제에서는 **pin_ptr** 배열의 첫 번째 요소의 위치를 제한 합니다.  
  
```cpp  
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
  
 다음 예제에서는 내부 포인터를 고정 포인터를 변환할 수 있는지 및 주소 연산자의 반환 형식 (`&`)는 피연산자가 관리 되는 힙에 내부 포인터입니다.  
  
```cpp  
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
  
 다음 예제에서는 고정 포인터를 다른 형식으로 캐스팅 될 수 있는지 보여 줍니다.  
  
```cpp  
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