---
title: '방법: PInvoke를 사용 하 여 배열 마샬링 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03e3cf184828c33c63c5252344eb0041640729cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>방법: PInvoke를 사용하여 배열 마샬링
이 항목에서는 CLR 문자열 형식을 사용 하 여 C 스타일 문자열을 호출할 수를 허용 하는 방법을 네이티브 함수를 설명 <xref:System.String> 지원.NET Framework 플랫폼 호출을 사용 하 여 합니다. Visual c + + 프로그래머는 P/Invoke는 작은 컴파일 타임 오류를 보고, 형식 안전 하지 않은 및는 것을 제공 하므로 (가능한 경우) 대신 c + + Interop 기능을 사용 하는 것이 좋습니다. P/Invoke 유일한 옵션은 관리 되지 않는 API는 DLL로 패키지 하는 경우 소스 코드를 사용할 수 없습니다 (그렇지 않은 경우 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).  
  
## <a name="example"></a>예제  
 네이티브 및 관리 되는 배열은 메모리에 다른 방식으로 배치 된, 때문에 변환 중 하나 또는 마샬링 필요는 관리 되 는/관리 되지 않는 경계를 넘어 성공적으로 전달 합니다. 이 항목에서는 관리 코드에서 네이티브 함수에 단순 (blitable) 항목의 배열에 전달 하는 방법  
  
 관리 되 는/관리 되지 않는 데이터는 일반적으로 마샬링 true 인는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성이 사용 되는 각 네이티브 함수에 대 한 관리 되는 진입점을 만드는 데 사용 됩니다. 배열을 인수로 사용 하는 함수의 경우는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 데이터를 마샬링하는 방법을 지정할 컴파일러에도 사용할 수 있습니다. 다음 예제에서는 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 관리 되는 배열의 C 스타일 배열로 마샬링하 나타내는 데 사용 됩니다.  
  
 다음 코드는 관리 되지 않는 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에는 정수 배열을 받는 함수를 정의 하는 DLL은입니다. 두 번째 모듈은이 기능을 하지만 관리 되는 배열 측면에서 정의 및 사용 하는 관리 되는 명령줄 응용 프로그램은 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 배열 호출 될 때 네이티브 배열을 변환 되어야 함을 지정 하는 특성입니다.  
  
 관리 되는 모듈은 /clr으로 컴파일됩니다.  
  
```cpp  
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
  
```cpp  
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
  
 DLL의 없는 일부는 기존를 통해 관리 되는 코드에 노출 되지 #include 지시문입니다. 실제로 DLL를 런타임 시 액세스 하므로 문제 함수를 사용 하 여 가져온 <xref:System.Runtime.InteropServices.DllImportAttribute> 컴파일 타임에 문제가 발견 되지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)