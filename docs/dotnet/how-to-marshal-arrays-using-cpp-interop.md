---
title: "방법: C++ Interop를 사용하여 배열 마샬링 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 마샬링"
  - "C++ Interop, 배열"
  - "데이터 마샬링[C++], 배열"
  - "interop[C++], 배열"
  - "마샬링[C++], 배열"
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++ Interop를 사용하여 배열 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목은 Visual C\+\+ 상호 운용성의 한 측면을 보여 줍니다.  자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
 다음 코드 예제에서는 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) \#pragma 지시문을 사용하여 동일한 파일에서 관리되는 함수와 관리되지 않는 함수를 구현합니다. 그러나 이러한 함수는 서로 다른 파일에 정의된 경우 동일한 방식으로 상호 운용됩니다.  관리되지 않는 함수만 포함된 파일은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 필요가 없습니다.  
  
## 예제  
 다음 예제에서는 관리되는 배열을 관리되지 않는 함수에 전달하는 방법을 보여 줍니다.  관리되는 함수에서는 관리되지 않는 함수를 호출하기 전에 배열에 대한 가비지 수집을 해제하기 위해 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)를 사용합니다.  GC 힙에 고정된 포인터를 관리되지 않는 함수에 제공하면 배열의 복사본을 만드는 데 따른 오버헤드를 방지할 수 있습니다.  관리되지 않는 함수가 GC 힙 메모리에 액세스하는 것을 보여 주기 위해 배열의 내용을 수정하고 관리되는 함수에서 컨트롤을 다시 시작할 때 변경 내용을 반영합니다.  
  
```  
// PassArray1.cpp  
// compile with: /clr  
#ifndef _CRT_RAND_S  
#define _CRT_RAND_S  
#endif  
  
#include <iostream>  
#include <stdlib.h>  
using namespace std;  
  
using namespace System;  
  
#pragma unmanaged  
  
void TakesAnArray(int* a, int c) {  
   cout << "(unmanaged) array received:\n";  
   for (int i=0; i<c; i++)  
      cout << "a[" << i << "] = " << a[i] << "\n";  
  
   unsigned int number;  
   errno_t err;  
  
   cout << "(unmanaged) modifying array contents...\n";  
   for (int i=0; i<c; i++) {  
      err = rand_s( &number );  
      if ( err == 0 )  
         a[i] = number % 100;  
   }  
}  
  
#pragma managed  
  
int main() {  
   array<int>^ nums = gcnew array<int>(5);  
  
   nums[0] = 0;  
   nums[1] = 1;  
   nums[2] = 2;  
   nums[3] = 3;  
   nums[4] = 4;  
  
   Console::WriteLine("(managed) array created:");  
   for (int i=0; i<5; i++)  
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);  
  
   pin_ptr<int> pp = &nums[0];  
   TakesAnArray(pp, 5);  
  
   Console::WriteLine("(managed) contents:");  
   for (int i=0; i<5; i++)  
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);  
}  
```  
  
## 예제  
 다음 예제에서는 관리되지 않는 배열을 관리되는 함수에 전달하는 방법을 보여 줍니다.  관리되는 함수는 관리되는 배열을 만들고 배열 내용을 복사하는 대신 배열 메모리에 직접 액세스하므로 관리되는 함수로 변경한 내용을 관리되지 않는 함수의 컨트롤이 회복될 때 이 함수에 반영할 수 있습니다.  
  
```  
// PassArray2.cpp  
// compile with: /clr   
#include <iostream>  
using namespace std;  
  
using namespace System;  
  
#pragma managed  
  
void ManagedTakesAnArray(int* a, int c) {  
   Console::WriteLine("(managed) array received:");  
   for (int i=0; i<c; i++)  
      Console::WriteLine("a[{0}] = {1}", i, a[i]);  
  
   cout << "(managed) modifying array contents...\n";  
   Random^ r = gcnew Random(DateTime::Now.Second);  
   for (int i=0; i<c; i++)  
      a[i] = r->Next(100);  
}  
  
#pragma unmanaged  
  
void NativeFunc() {  
   int nums[5] = { 0, 1, 2, 3, 4 };  
  
   printf_s("(unmanaged) array created:\n");  
   for (int i=0; i<5; i++)  
      printf_s("a[%d] = %d\n", i, nums[i]);  
  
   ManagedTakesAnArray(nums, 5);  
  
   printf_s("(ummanaged) contents:\n");  
   for (int i=0; i<5; i++)  
      printf_s("a[%d] = %d\n", i, nums[i]);  
}  
  
#pragma managed  
  
int main() {  
   NativeFunc();  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)