---
title: "방법: PInvoke를 사용 하 여 문자열 마샬링 | Microsoft Docs"
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
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1887a88bcfcdec9daf2661eca56a0adcf59ba08
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>방법: PInvoke를 사용하여 문자열 마샬링
이 항목에서는 CLR 문자열을 사용 하 여 C 스타일 문자열을 호출할 수를 허용 하는 방법을 네이티브 함수를 설명 지원을.NET Framework 플랫폼 호출을 사용 하 여 system:: string을 입력 합니다. Visual c + + 프로그래머는 P/Invoke는 작은 컴파일 타임 오류를 보고, 형식 안전 하지 않은 및는 것을 제공 하므로 (가능한 경우) 대신 c + + Interop 기능을 사용 하는 것이 좋습니다. 관리 되지 않는 API는 DLL로 패키지 되어 소스 코드를 사용할 수 없는 경우 다음 P/Invoke 유일한 옵션은 있지만 그렇지 않은 경우 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.  
  
 필요 하므로 관리 되는 관리 되지 않는 함수에서 문자열을 전달 스레드와 관리 되지 않는 문자열은 메모리에 다른 방식으로 배치 된을 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 문자열 데이터를 마샬링하기 위한 필요한 변환 메커니즘을 삽입 하도록 컴파일러에 지시 하는 특성 올바르고 안전 하 게 합니다.  
  
 내장 데이터 형식만 사용 하는 함수의 <xref:System.Runtime.InteropServices.DllImportAttribute> 는 네이티브 함수에 하지만 C 스타일 문자열에 대 한 핸들을 사용 하도록 이러한 진입점을 정의 하는 대신 문자열을 전달 하기 위한 관리 되는 진입점을 선언 하는 데 사용 되는 <xref:System.String> 유형 대신 사용할 수 있습니다. 이 메시지는 필요한 변환을 수행 하는 코드를 삽입 하도록 컴파일러에 표시 합니다. 각 함수 인수는 문자열을 사용 하는 관리 되지 않는 함수에 대해는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열 개체를 C 스타일 문자열로 네이티브 함수에 마샬링되어야 한다는 것을 나타내기 위해 사용 해야 합니다.  
  
## <a name="example"></a>예  
 다음 코드는 관리 되지 않는 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈은 TakesAString char *의 형태로 ANSI C 스타일 문자열을 수락 하는 호출 하는 함수를 정의 하는 DLL입니다. 관리 되는 모듈 TakesAString 함수 가져오지만 char 대신 관리 되는 System.String를 사용 하도록 정의 하는 명령줄 응용 프로그램은\*합니다. <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 TakesAString 호출 될 때 관리 되는 문자열을 마샬링하는 방법을 나타내는 데 사용 됩니다.  
  
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
  
 이 방법을 사용 하면 네이티브 함수에서 문자열에 변경한 문자열의 관리 되는 복사본에 반영 되지 것입니다 하므로 관리 되지 않는 힙에서 생성 되는 문자열의 복사본입니다.  
  
 DLL의 없는 일부는 기존를 통해 관리 되는 코드에 노출 되지 #include 지시문입니다. 사실, DLL은 액세스할 런타임에만 문제 함수를 사용 하 여 가져온 `DllImport` 컴파일 타임에 문제가 발견 되지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)