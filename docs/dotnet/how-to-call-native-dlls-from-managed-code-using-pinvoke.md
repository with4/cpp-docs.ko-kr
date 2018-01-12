---
title: "방법: PInvoke를 사용 하 여 관리 되는 코드에서 네이티브 Dll 호출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d22f493a582b6ef09615f94c7b321a7cc535e5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출
플랫폼 호출 (P/Invoke) 기능을 사용 하 여 관리 코드에서 관리 되지 않는 Dll에서 구현 되는 함수를 호출할 수 있습니다. DLL에 대 한 소스 코드를 사용할 수 없는 경우 P/Invoke 상호 운용 하기 위한 유일한 옵션입니다. 그러나 다른.NET 언어와 달리 Visual c + + P/Invoke에 대 한 대안을 제공합니다. 자세한 내용은 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 Win32 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) 현재 픽셀의 화면 해상도 검색 하는 함수입니다.  
  
 을 인수로 내장 형식만 사용 하 고 값을 반환 하는 함수 추가 작업이 필요 합니다. 함수 포인터, 배열 및 구조 등의 다른 데이터 형식이 추가 특성을 적절 한 데이터 마샬링을 확인 해야 합니다.  
  
 필요 하지 않은 이지만이 예제에서와 같이 전역 네임 스페이스에 존재 하지 않는 있도록 P/Invoke 선언 값 클래스의 정적 멤버를 만들 것이 좋습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)