---
title: "방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출 | Microsoft Docs"
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
  - "데이터 마샬링[C++], 네이티브 DLL 호출"
  - "interop[C++], 네이티브 DLL 호출"
  - "마샬링[C++], 네이티브 DLL 호출"
  - "플랫폼 호출[C++], 네이티브 DLL 호출"
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# 방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

관리되는 DLL에서 구현되는 함수는 P\/Invoke\(플랫폼 호출\) 기능을 사용하여 관리 코드에서 호출할 수 있습니다.  DLL의 소스 코드를 사용할 수 없는 경우에는 P\/Invoke가 유일한 상호 운용 옵션으로 제공됩니다.  그러나 다른 .NET 언어와 달리 Visual C\+\+에서는 P\/Invoke에 대한 대체 기능을 제공합니다.  자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 Win32 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) 함수를 사용하여 화면의 현재 해상도를 픽셀 단위로 검색합니다.  
  
 인수와 반환 값으로 내장 형식만 사용하는 함수의 경우 별도의 작업이 필요하지 않습니다.  함수 포인터, 배열, 구조체 등과 같은 다른 데이터 형식의 경우 데이터를 올바르게 마샬링하는 데 필요한 특성을 추가로 사용해야 합니다.  
  
 필수 요구 사항은 아니지만 이 예제에서와 같이 P\/Invoke 선언을 값 클래스의 정적 멤버로 만들어 전역 네임스페이스에 포함되지 않도록 하는 것이 좋습니다.  
  
```  
// pinvoke_basic.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value class Win32 {  
public:  
   [DllImport("User32.dll")]  
   static int GetSystemMetrics(int);  
  
   enum class SystemMetricIndex {  
      // Same values as those defined in winuser.h.  
      SM_CXSCREEN = 0,  
      SM_CYSCREEN = 1  
   };  
};  
  
int main() {  
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );  
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );  
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);  
}  
```  
  
## 참고 항목  
 [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)