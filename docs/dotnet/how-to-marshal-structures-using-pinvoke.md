---
title: '방법: PInvoke를 사용 하 여 구조체 마샬링 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e7f08d42946eec22d616e6d964feda78e1358228
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>방법: PInvoke를 사용하여 구조체 마샬링
이 문서에서는 어떻게 네이티브 함수를 P/Invoke를 사용 하 여 관리 되는 함수에서 C 스타일 구조체를 호출할 수 있습니다. 있지만 대신 c + + Interop 기능을 사용 하는 것이 좋습니다 P/Invoke P/Invoke 거의 컴파일 타임 오류 보고를 제공 하기 때문에 형식이 안전한 아니며 관리 되지 않는 API는 DLL로 패키지와 소스 코드를 없는 경우 구현 하는 것 P/Invoke를 사용할 수 있는 유일한 옵션입니다. 다음 문서를 참조 하십시오.  
  
-   [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
  
-   [방법: PInvoke를 사용하여 문자열 마샬링](../dotnet/how-to-marshal-strings-using-pinvoke.md)
  
 기본적으로 네이티브 및 관리 되는 구조에에서으로 배치 된 다르게 메모리 성공적 데이터 무결성을 유지 하기 위해 추가 단계를 필요로 하는 관리 되 는/관리 되지 않는 경계의 구조체를 전달 합니다.  
  
 이 문서에서는 기본 구조와 관리 되지 않는 함수에 결과 구조체를 전달 하는 방법의 관리 되는 해당 항목을 정의 하는 데 필요한 단계를 설명 합니다. 이 문서에서는 가정 하는 간단한 구조-문자열이 나 포인터를 포함 하지 않는 것-사용 됩니다. 비 blittable 상호 운용성에 대 한 정보를 참조 하십시오. [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다. P/Invoke의 반환 값으로 비 blittable 형식을 가질 수 없습니다. Blittable 형식 코드와 비관리 코드에서 표현이 동일한. 자세한 내용은 참조 [blittable 형식 및 비 Blittable 형식](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)합니다.  
  
 단순 마샬링, 관리 되 는/관리 되지 않는 경계를 넘어 blittable 구조 먼저 필요 각 네이티브 구조체의 관리 되는 버전을 정의 하는 것 합니다. 이러한 구조 이름에는 제한이 법적; 두 개의 구조는 데이터 레이아웃 이외의 네이티브 및 관리 되는 버전 간의 관계가 없습니다. 따라서이 관리 되는 버전 크기 및 네이티브 것과 동일한 순서로 동일한 필드가 포함 되어 있음을 중요 합니다. (메커니즘은 없습니다 구조체의 관리 및 네이티브 버전 모두 동일 하므로 비 호환성 드러나지 않습니다 런타임이 될 때까지 보장 합니다. 이 두 구조체는 동일한 데이터 레이아웃을 갖도록 하는 데 프로그래머의 책임입니다.)  
  
 사용 해야 하는 성능 향상을 위해 관리 되는 구조체의 멤버를 다시 정렬할 경우에 따라, 때문에 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 나타내는 구조 순차적으로 배치 됩니다. 또한 구조체 압축 네이티브 구조체에서 사용 하는 것과 동일 하 게 설정을 명시적으로 설정 하는 것이 좋습니다. (기본적으로 Visual c + + 사용는 8 바이트 구조체 모두 관리 되는 코드에 대 한 압축 합니다.)  
  
1.  를 사용 하 여 <xref:System.Runtime.InteropServices.DllImportAttribute> 구조를 사용 하는 모든 관리 되지 않는 함수에 해당 하는 진입점을 선언 하지만의 두 버전 모두에 동일한 이름을 사용 하는 경우 함수 서명이 있는 구조체의 관리 되는 버전을 사용 하는 구조입니다.  
  
2.  이제 관리 되는 코드 관리 되지 것으로 관리 되지 않는 함수에 구조체의 관리 되는 버전을 전달할 수 있습니다. 이러한 구조는 다음 예제와 같이 값 이나 참조로 전달할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 관리 되지 않는 관리 되는 모듈 구성 됩니다. 관리 되지 않는 모듈에는 위치 및 위치 구조의 두 인스턴스를 허용 하는 GetDistance를 호출 하는 함수를 호출 하는 구조를 정의 하는 DLL은입니다. 두 번째 모듈은 GetDistance 함수 가져오지만 MLocation 위치 구조체의 관리 되는 항목 측면에서 정의 하는 관리 되는 명령줄 응용 프로그램. 연습; 구조체의 두 버전에 대해 동일한 이름을 사용할 것은 그러나 다른 이름은 DllImport 프로토타입 관리 되는 버전 측면에서 정의 됨을 보여 주기 위해 여기 사용 됩니다.  
  
 DLL의 없는 일부는 기존 사용 하 여 관리 코드에 노출 되지 #include 지시문입니다. 사실, 컴파일 타임에 DllImport를 사용 하 여 가져온 기능에서 문제가 검색 되지 하므로 런타임 시만 DLL 액세스 됩니다.  
  
```  
// TraditionalDll3.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#include <stdio.h>  
#include <math.h>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
   #define TRADITIONALDLL_API __declspec(dllexport)  
#else  
   #define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct Location {  
   int x;  
   int y;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API double GetDistance(Location, Location);  
   TRADITIONALDLL_API void InitLocation(Location*);  
}  
  
double GetDistance(Location loc1, Location loc2) {  
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   printf_s("[unmanaged] Initializing location...\n");  
   lp->x = 50;  
   lp->y = 50;  
}  
```  
  
## <a name="example"></a>예제  
  
```  
// MarshalStruct_pi.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MLocation {  
   int x;  
   int y;  
};  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL3.dll")]  
   static public double GetDistance(MLocation, MLocation);  
   [DllImport("TraditionalDLL3.dll")]  
   static public double InitLocation(MLocation*);  
};  
  
int main() {  
   MLocation loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   MLocation loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = TraditionalDLL::GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   MLocation loc3;  
   TraditionalDLL::InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
```Output  
[unmanaged] loc1(0,0) loc2(100,100)  
[managed] distance = 141.42135623731  
[unmanaged] Initializing location...  
[managed] x=50 y=50  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
