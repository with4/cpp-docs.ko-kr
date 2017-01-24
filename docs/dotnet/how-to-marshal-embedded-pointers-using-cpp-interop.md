---
title: "방법: C++ Interop를 사용하여 포함 포인터 마샬링 | Microsoft Docs"
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
  - "C++ Interop, 포함 포인터"
  - "데이터 마샬링[C++], 포함 포인터"
  - "interop[C++], 포함 포인터"
  - "마샬링[C++], 포함 포인터"
  - "포인터[C++], 마샬링"
  - "구조체[C++], 포함 포인터 마샬링"
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C++ Interop를 사용하여 포함 포인터 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md) \#pragma 지시문을 사용하여 동일한 파일에서 관리되는 함수와 관리되지 않는 함수를 구현합니다. 그러나 이러한 함수는 서로 다른 파일에 정의된 경우 동일한 방식으로 상호 운용됩니다.  관리되지 않는 함수만 포함된 파일은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일할 필요가 없습니다.  
  
## 예제  
 다음 예제에서는 포인터를 포함하는 구조체를 매개 변수로 사용하는 관리되지 않는 함수를 관리되는 함수에서 호출할 수 있는 이유를 보여 줍니다.  관리되는 함수에서는 구조체의 인스턴스를 만들고 포함된 포인터를 [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) 키워드 대신 new 키워드로 초기화합니다.  이렇게 하면 메모리가 네이티브 힙에서 할당되므로 가비지 수집을 막기 위해 배열을 고정시킬 필요가 없습니다.  그러나 메모리 누수를 피하려면 메모리를 명시적으로 삭제해야 합니다.  
  
```  
// marshal_embedded_pointer.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// unmanaged struct  
struct ListStruct {  
   int count;  
   double* item;  
};  
  
#pragma unmanaged  
  
void UnmanagedTakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
  
#pragma managed  
  
int main() {  
   ListStruct list;  
   list.count = 10;  
   list.item = new double[list.count];  
  
   Console::WriteLine("[managed] count = {0}", list.count);  
   Random^ r = gcnew Random(0);  
   for (int i=0; i<list.count; i++) {  
      list.item[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);  
   }  
  
   UnmanagedTakesListStruct( list );  
   delete list.item;  
}  
```  
  
  **\[managed\] count \= 10**  
**array\[0\] \= 72.624326996796**  
**array\[1\] \= 81.7325359590969**  
**array\[2\] \= 76.8022689394663**  
**array\[3\] \= 55.8161191436537**  
**array\[4\] \= 20.6033154021033**  
**array\[5\] \= 55.8884794618415**  
**array\[6\] \= 90.6027066011926**  
**array\[7\] \= 44.2177873310716**  
**array\[8\] \= 97.754975314138**  
**array\[9\] \= 27.370445768987**  
**\[unmanaged\] count \= 10**  
**array\[0\] \= 72.624327**  
**array\[1\] \= 81.732536**  
**array\[2\] \= 76.802269**  
**array\[3\] \= 55.816119**  
**array\[4\] \= 20.603315**  
**array\[5\] \= 55.888479**  
**array\[6\] \= 90.602707**  
**array\[7\] \= 44.217787**  
**array\[8\] \= 97.754975**  
**array\[9\] \= 27.370446**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)