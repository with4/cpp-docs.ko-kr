---
title: "방법: PInvoke를 사용 하 여 포인터를 포함 하는 마샬링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cd2717e5ffc5dc25f7a98f679a23d6f97fd335a5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>방법: PInvoke를 사용하여 포함 포인터 마샬링
플랫폼 호출 (P/Invoke) 기능을 사용 하 여 관리 코드에서 관리 되지 않는 Dll에서 구현 되는 함수를 호출할 수 있습니다. DLL에 대 한 소스 코드를 사용할 수 없는 경우 P/Invoke 상호 운용 하기 위한 유일한 옵션입니다. 그러나 다른.NET 언어와 달리 Visual c + + P/Invoke에 대 한 대안을 제공합니다. 자세한 내용은 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) 및 [하는 방법: 마샬링 포함 된 포인터를 사용 하 여 c + + Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)합니다.  
  
## <a name="example"></a>예  
 구조체를 네이티브 코드로 전달 네이티브 구조체에 데이터 레이아웃 측면에서 해당 하는 관리 되는 구조 만들어졌는지 필요 합니다. 그러나 포인터를 포함 하는 구조체에는 특별 한 처리가 필요 합니다. 기본 구조에 포함 된 각 포인터에 대 한 구조체의 관리 되는 버전의 인스턴스를 포함 해야는 <xref:System.IntPtr> 유형입니다. 또한 메모리 이러한 인스턴스를 명시적으로 할당 해야에 대 한 초기화 및 사용 하 여 해제 된 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, 및 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> 메서드.  
  
 다음 코드는 관리 되지 않는 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에 대 한 포인터를 포함 하는 ListString 라고 하는 구조를 허용 하는 함수 및 TakesListStruct를 호출 하는 함수를 정의 하는 DLL은. 관리 되는 모듈 TakesListStruct 함수 및 호출 MListStruct 제외 하 고 double *로 표시 됩니다 네이티브 ListStruct에 해당 하는 구조를 정의 하는 명령줄 응용 프로그램은 프로그램 <xref:System.IntPtr> 인스턴스. Main 함수 TakesListStruct를 호출 하기 전에 할당 하 고이 필드를 참조 하는 메모리를 초기화 합니다.  
  
```cpp  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```cpp  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 DLL의 없는 일부는 기존 사용 하 여 관리 코드에 노출 되지 #include 지시문입니다. 사실, DLL에 액세스 하 게 실행된 시간에만 사용 하 여 가져온 함수에 문제가 있으므로 <xref:System.Runtime.InteropServices.DllImportAttribute> 컴파일 타임에 문제가 발견 되지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)