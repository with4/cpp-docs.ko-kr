---
title: '방법: c + + Interop를 사용 하 여 포인터를 포함 하는 마샬링 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structures [C++], marshaling embedded pointers
- interop [C++], embedded pointers
- C++ Interop, embedded pointers
- marshaling [C++], embedded pointers
- pointers [C++], marshaling
- data marshaling [C++], embedded pointers
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3f0dab57fd9962975271d8105de64c729c6095fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129007"
---
# <a name="how-to-marshal-embedded-pointers-using-c-interop"></a>방법: C++ Interop를 사용하여 포함 포인터 마샬링
다음 코드 예제에서 사용 된 [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md) #pragma 지시문을 구현 하 관리는 관리 되지 않는 함수에서 동일한 파일에 별도 파일에 정의 된 경우 이러한 함수가 동일한 방식으로 상호 운용 합니다. 관리 되지 않는 함수만 포함 된 파일 사용 하 여 컴파일할 필요가 없습니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 관리 되는 함수에서 포인터를 포함 하는 구조를 사용 하는 관리 되지 않는 함수를 호출할 수 방법을 보여 줍니다. 관리 되는 함수는 구조체의 인스턴스를 만들고 새 키워드와 함께 포함된 된 포인터를 초기화 합니다 (대신는 [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) 키워드)입니다. 없기 때문에 네이티브 힙에 메모리를 할당이 가비지 수집을 위해 배열을 고정 필요가 없습니다. 그러나 메모리 누수를 방지 하기 위해 메모리를 명시적으로 삭제 해야 합니다.  
  
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
  
```Output  
[managed] count = 10  
array[0] = 72.624326996796  
array[1] = 81.7325359590969  
array[2] = 76.8022689394663  
array[3] = 55.8161191436537  
array[4] = 20.6033154021033  
array[5] = 55.8884794618415  
array[6] = 90.6027066011926  
array[7] = 44.2177873310716  
array[8] = 97.754975314138  
array[9] = 27.370445768987  
[unmanaged] count = 10  
array[0] = 72.624327  
array[1] = 81.732536  
array[2] = 76.802269  
array[3] = 55.816119  
array[4] = 20.603315  
array[5] = 55.888479  
array[6] = 90.602707  
array[7] = 44.217787  
array[8] = 97.754975  
array[9] = 27.370446  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)