---
title: "방법: PInvoke를 사용하여 함수 포인터 마샬링 | Microsoft Docs"
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
  - "데이터 마샬링[C++], 콜백 및 대리자"
  - "interop[C++], 콜백 및 대리자"
  - "마샬링[C++], 콜백 및 대리자"
  - "플랫폼 호출[C++], 콜백 및 대리자"
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: PInvoke를 사용하여 함수 포인터 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 .NET Framework P\/Invoke 기능을 사용하여 관리되지 않는 함수와 상호 운용할 때 함수 포인터 대신 관리되는 대리자를 사용하는 방법에 대해 설명합니다.  Visual 그러나 C\+\+ 프로그래머는 가능한 한 C\+\+ Interop 기능을 대신 사용하는 것이 좋습니다. P\/Invoke는 컴파일 타임 오류를 거의 보고하지 않으며 형식이 안전하지 않고 구현이 복잡할 수 있기 때문입니다.  관리되지 않는 API가 DLL로 패키지되어 있고 소스 코드를 사용할 수 없는 경우에는 P\/Invoke만 사용할 수 있습니다.  또한 다음 항목도 참조하십시오.  
  
-   [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [방법: C\+\+ Interop를 사용하여 콜백 및 대리자 마샬링](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 함수 포인터를 인수로 사용하는 관리되지 않는 API는 네이티브 함수 포인터 대신 관리되는 대리자를 사용하여 관리 코드에서 호출할 수 있습니다.  컴파일러는 관리되지 않는 함수에 대한 대리자를 함수 포인터로 자동 마샬링하고 필요한 관리\/비관리 전환 코드를 삽입합니다.  
  
## 예제  
 다음 코드는 관리되지 않는 모듈과 관리되는 모듈로 구성되어 있습니다.  관리되지 않는 모듈은 함수 포인터를 받아들이는 TakesCallback이라는 함수를 정의하는 DLL입니다.  이 주소는 함수를 실행하는 데 사용됩니다.  
  
 관리되는 모듈은 네이티브 코드에 함수 포인터로 마샬링되는 대리자를 정의하고 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 사용하여 네이티브 TakesCallback 함수를 관리 코드에 노출합니다.  main 함수에서는 대리자의 인스턴스가 작성되고 TakesCallback 함수에 전달됩니다.  프로그램 출력에서는 네이티브 TakesCallback 함수를 통해 이 함수가 실행되었음을 보여 줍니다.  
  
 관리되는 함수는 .NET Framework 가비지 수집으로 인해 네이티브 함수를 실행하는 동안 대리자가 재배치되지 않도록 방지하기 위해 관리되는 대리자에 대한 가비지 수집을 중단합니다.  
  
 관리되는 모듈은 \/CLR을 사용하여 컴파일되지만 \/clr:pure를 사용해도 컴파일됩니다.  
  
```  
// TraditionalDll5.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   /* Declare an unmanaged function type that takes two int arguments  
      Note the use of __stdcall for compatibility with managed code */  
   typedef int (__stdcall *CALLBACK)(int);  
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);  
}  
  
int TakesCallback(CALLBACK fp, int n) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n);  
}  
```  
  
```  
// MarshalDelegate.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
public delegate int GetTheAnswerDelegate(int);  
public value struct TraditionalDLL {  
   [DllImport("TraditionalDLL5.dll")]  
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);  
};  
  
int GetNumber(int n) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
   return x + n;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TraditionalDLL::TakesCallback(fp, 42);  
}  
```  
  
 DLL의 어떠한 부분도 일반적인 \#include 지시문을 사용하여 관리 코드에 노출되지 않습니다.  실제로는 런타임에만 DLL에 액세스하므로 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 가져온 함수에 문제가 있더라도 컴파일할 때는 그러한 문제가 발견되지 않습니다.  
  
## 참고 항목  
 [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)