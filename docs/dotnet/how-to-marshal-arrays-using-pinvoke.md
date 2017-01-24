---
title: "방법: PInvoke를 사용하여 배열 마샬링 | Microsoft Docs"
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
  - "데이터 마샬링[C++], 배열"
  - "interop[C++], 배열"
  - "마샬링[C++], 배열"
  - "플랫폼 호출[C++], 배열"
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: PInvoke를 사용하여 배열 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 .NET Framework 플랫폼 호출 지원으로 <xref:System.String> CLR 문자열 형식을 사용하여 C 스타일 문자열이 허용되는 네이티브 함수를 호출하는 방법에 대해 설명합니다.  Visual C\+\+ 프로그래머는 가능한 한 C\+\+ Interop 기능을 대신 사용하는 것이 좋습니다. P\/Invoke는 컴파일 타임 오류 보고를 거의 제공하지 않으며 형식이 안전하지 않을 뿐만 아니라 구현 작업이 번거로울 수 있기 때문입니다.  관리되지 않는 API가 DLL로 패키지되어 있고 소스 코드를 사용할 수 없는 경우에는 P\/Invoke만 사용할 수 있습니다. 그렇지 않으면 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
## 예제  
 네이티브 배열과 관리되는 배열은 메모리에 서로 다른 방식으로 배치되므로 관리\/비관리 경계를 지나 이러한 배열을 전달하려면 마샬링이라고 하는 변환이 필요합니다.  이 항목에서는 관리 코드에서 네이티브 함수로 간단한 blittable 항목의 배열을 전달하는 방법을 보여 줍니다.  
  
 관리\/비관리 데이터 마샬링에 일반적으로 적용되는 것과 마찬가지로, 사용할 각 네이티브 함수에 대한 관리되는 진입점을 만드는 데는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성이 사용됩니다.  배열을 인수로 사용하는 함수의 경우 컴파일러에서 데이터를 마샬링하는 방식을 지정하기 위한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성도 함께 사용해야 합니다.  다음 예제에서는 관리되는 배열을 C 스타일 배열로 마샬링하도록 지정하기 위해 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형을 사용합니다.  
  
 다음 코드는 관리되지 않는 모듈과 관리되는 모듈로 구성되어 있습니다.  관리되지 않는 모듈은 정수 배열을 받는 함수를 정의하는 DLL입니다.  두 번째 모듈은 이 함수를 가져오지만 이를 관리되는 배열의 측면에서 정의하는 관리되는 명령줄 응용 프로그램입니다. 여기서는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 호출 시 배열을 네이티브 배열로 변환하도록 지정합니다.  
  
 관리되는 모듈은 \/CLR을 사용하여 컴파일되지만 \/clr:pure를 사용해도 컴파일됩니다.  
  
```  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 일반적인 \#include 지시문을 통해서는 DLL의 어떠한 부분도 관리 코드에 노출되지 않습니다.  실제로는 런타임에만 DLL에 액세스하므로 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 가져온 함수에 문제가 있더라도 컴파일할 때는 그러한 문제가 발견되지 않습니다.  
  
## 참고 항목  
 [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)