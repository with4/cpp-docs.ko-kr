---
title: "방법: PInvoke를 사용하여 포함 포인터 마샬링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 마샬링[C++], 포함 포인터"
  - "포함 포인터[C++]"
  - "interop[C++], 포함 포인터"
  - "마샬링[C++], 포함 포인터"
  - "플랫폼 호출[C++], 포함 포인터"
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: PInvoke를 사용하여 포함 포인터 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

관리되는 DLL에서 구현되는 함수는 P\/Invoke\(플랫폼 호출\) 기능을 사용하여 관리 코드에서 호출할 수 있습니다.  DLL의 소스 코드를 사용할 수 없는 경우에는 P\/Invoke가 유일한 상호 운용 옵션으로 제공됩니다.  그러나 다른 .NET 언어와 달리 Visual C\+\+에서는 P\/Invoke에 대한 대체 기능을 제공합니다.  자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md) 및 [방법: C\+\+ Interop를 사용하여 포함 포인터 마샬링](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)를 참조하십시오.  
  
## 예제  
 구조체를 네이티브 코드에 전달하려면 네이티브 구조체와 데이터 레이아웃이 동일한 관리되는 구조체를 만들어야 합니다.  그러나 포인터가 포함된 구조체에는 특별한 처리 방식이 필요합니다.  네이티브 구조체에 포함된 각 포인터에 대해 관리되는 버전의 구조체에는 <xref:System.IntPtr> 형식의 인스턴스가 들어 있어야 합니다.  또한 이러한 인스턴스의 메모리는 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> 및 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> 메서드를 사용하여 명시적으로 할당, 초기화 및 해제해야 합니다.  
  
 다음 코드는 관리되지 않는 모듈과 관리되는 모듈로 구성되어 있습니다.  관리되지 않는 모듈은 TakesListStruct라는 함수와 포인터가 포함된 ListString이라는 구조체를 사용하는 함수를 정의하는 DLL입니다.  관리되는 모듈은 TakesListStruct 함수를 가져오는 명령줄 응용 프로그램입니다. 이 응용 프로그램에서는 double\*이 <xref:System.IntPtr> 인스턴스로 표현된다는 점을 제외하고는 네이티브 ListStruct와 동일한 MListStruct라는 구조체를 정의합니다.  TakesListStruct를 호출하기 전에 main 함수는 이 필드가 참조하는 메모리를 할당하고 초기화합니다.  
  
 관리되는 모듈은 \/CLR을 사용하여 컴파일되지만 \/clr:pure를 사용해도 컴파일됩니다.  
  
```  
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
  
```  
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
  
 DLL의 어떠한 부분도 일반적인 \#include 지시문을 사용하여 관리 코드에 노출되지 않습니다.  실제로는 런타임에만 DLL에 액세스하므로 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 가져온 함수에 문제가 있더라도 컴파일할 때는 그러한 문제가 발견되지 않습니다.  
  
## 참고 항목  
 [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)