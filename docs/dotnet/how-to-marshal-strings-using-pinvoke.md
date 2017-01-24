---
title: "방법: PInvoke를 사용하여 문자열 마샬링 | Microsoft Docs"
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
  - "데이터 마샬링[C++], 문자열"
  - "interop[C++], 문자열"
  - "마샬링[C++], 문자열"
  - "플랫폼 호출[C++], 문자열"
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: PInvoke를 사용하여 문자열 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 .NET Framework 플랫폼 호출 지원으로 System::String CLR 문자열 형식을 사용하여 C 스타일 문자열이 허용되는 네이티브 함수를 호출하는 방법에 대해 설명합니다.  Visual C\+\+ 프로그래머는 가능한 한 C\+\+ Interop 기능을 대신 사용하는 것이 좋습니다. P\/Invoke는 컴파일 타임 오류 보고를 거의 제공하지 않으며 형식이 안전하지 않을 뿐만 아니라 구현 작업이 번거로울 수 있기 때문입니다.  관리되지 않는 API가 DLL로 패키지되어 있고 소스 코드를 사용할 수 없는 경우에는 P\/Invoke만 사용할 수 있습니다. 그렇지 않으면 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
 관리되는 문자열과 관리되지 않는 문자열은 메모리에 서로 다른 방식으로 배치되므로 관리되는 함수에서 관리되지 않는 함수로 문자열을 전달하려면 문자열 데이터를 올바르고 안전하게 마샬링하기 위해 필요한 변환 메커니즘을 삽입하도록 컴파일러에 지시하는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성이 필요합니다.  
  
 내장 데이터 형식만 사용하는 함수의 경우 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 네이티브 함수에 대한 관리되는 진입점을 선언해야 하지만, 문자열을 전달할 때는 C 스타일 문자열을 사용하도록 이러한 진입점을 정의하는 대신 <xref:System.String> 형식에 대한 핸들을 사용할 수 있습니다.  이 경우 필요한 변환을 수행하는 코드를 삽입하라는 메시지가 컴파일러에 표시됩니다.  문자열을 입력받는 관리되지 않는 함수의 각 함수 인수에 대해 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 String 개체를 C 스타일 문자열로서 네이티브 함수로 마샬링하도록 지정해야 합니다.  
  
## 예제  
 다음 코드는 관리되지 않는 모듈과 관리되는 모듈로 구성되어 있습니다.  관리되지 않는 모듈은 C 스타일 ANSI 문자열을 char\*의 형태로 전달받는 TakesAString이라는 함수를 정의하는 DLL입니다.  관리되는 모듈은 TakesAString 함수를 가져오지만 이 함수를 char\* 대신 관리되는 System.String으로 가져오도록 정의하는 명령줄 응용 프로그램입니다.  TakesAString을 호출할 때 관리되는 문자열을 어떻게 마샬링할지 지정하는 데는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성이 사용됩니다.  
  
 관리되는 모듈은 \/CLR을 사용하여 컴파일되지만 \/clr:pure를 사용해도 컴파일됩니다.  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 이 방법을 사용하면 관리되지 않는 힙에 문자열의 복사본이 생성되므로 네이티브 함수로 문자열을 변경한 내용은 문자열의 관리되는 복사본에 반영되지 않습니다.  
  
 일반적인 \#include 지시문을 통해서는 DLL의 어떠한 부분도 관리 코드에 노출되지 않습니다.  실제로는 런타임에만 DLL에 액세스하므로 `DllImport`를 사용하여 가져온 함수에 문제가 있더라도 컴파일할 때는 그러한 문제가 발견되지 않습니다.  
  
## 참고 항목  
 [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)