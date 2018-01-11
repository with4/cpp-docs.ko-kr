---
title: "방법: PInvoke를 사용 하 여 함수 포인터 마샬링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cf7f23ea9337b499d4ec80b19e3104074429cc71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>방법: PInvoke를 사용하여 함수 포인터 마샬링
이 항목에서는 관리 되는 방식을 대리자 설명 관리 되지 않는.NET Framework P/Invoke 기능을 사용 하 여 함수 리소스와 상호 운용 하는 경우 함수 포인터 대신 사용할 수 있습니다. 그러나 Visual c + + 프로그래머는 P/Invoke는 작은 컴파일 타임 오류를 보고, 형식 안전 하지 않은 및는 것을 제공 하므로 (가능한 경우) 대신 c + + Interop 기능을 사용 하는 것이 좋습니다. 관리 되지 않는 API는 DLL로 패키지 하는 경우 소스 코드를 사용할 수 없는 P/Invoke 유일한 옵션입니다. 다음 항목을 참조 하십시오.  
  
-   [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [방법: C++ Interop를 사용하여 콜백 및 대리자 마샬링](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 관리 되지 않는 Api에서 인수를 호출 될 함수 포인터는 네이티브 함수 포인터 대신 관리 되는 대리자를 사용 하 여 코드를 관리 합니다. 컴파일러는 자동으로 관리 되지 않는 함수에 대 한 함수 포인터로 대리자 마샬링합니다 하 고 필요한 관리 되 는/관리 되지 않는 변환 코드를 삽입 합니다.  
  
## <a name="example"></a>예  
 다음 코드는 관리 되지 않는 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈은 TakesCallback 함수 포인터를 허용 하 라는 함수를 정의 하는 DLL입니다. 이 주소는 함수 실행에 사용 됩니다.  
  
 함수 포인터는 네이티브 코드로 마샬링 하 고 사용 하는 대리자를 정의 하는 관리 되는 모듈의 <xref:System.Runtime.InteropServices.DllImportAttribute> 관리 코드에 네이티브 TakesCallback 함수를 노출 하는 특성입니다. Main 함수에 대리자의 인스턴스가 생성 되어 TakesCallback 함수에 전달 합니다. 프로그램 출력이이 함수가 네이티브 TakesCallback 함수에 의해 실행 되는 방법을 보여 줍니다.  
  
 관리 되는 함수에는 네이티브 함수를 실행 하는 동안 대리자가 재배치에서.NET Framework 가비지 수집을 방지 하기 위해 관리 되는 대리자에 대 한 가비지 수집을 하지 않습니다.  
  
 관리 되는 모듈, /clr 하지만 /clr을 사용 하 여 컴파일되며: pure 합니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
```cpp  
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
  
```cpp  
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
  
 DLL의 없는 일부는 기존 사용 하 여 관리 코드에 노출 되지 #include 지시문입니다. 사실, DLL에 액세스 하 게 실행된 시간에만 사용 하 여 가져온 함수에 문제가 있으므로 <xref:System.Runtime.InteropServices.DllImportAttribute> 컴파일 타임에 문제가 발견 되지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)