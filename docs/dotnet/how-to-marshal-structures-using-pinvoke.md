---
title: "방법: PInvoke를 사용하여 구조체 마샬링 | Microsoft Docs"
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
  - "데이터 마샬링[C++], 구조체"
  - "interop[C++], 구조체"
  - "마샬링[C++], 구조체"
  - "플랫폼 호출[C++], 구조체"
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# 방법: PInvoke를 사용하여 구조체 마샬링
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 P\/Invoke를 사용하여 <xref:System.String> 인스턴스를 제공하는 관리되는 함수에서 C 스타일 문자열에 액세스하는 네이티브 함수를 호출하는 방법에 대해 설명합니다.  P\/Invoke는 컴파일 타임 오류 보고를 거의 제공하지 않고, 형식이 안전하지 않으며, 구현하기 번거로울 수도 있으므로 P\/Invoke 대신 C\+\+ Interop 기능을 사용하는 것이 좋지만 관리되지 않는 API가 DLL로 패키징되었으며 소스 코드를 사용할 수 없는 경우 P\/Invoke가 유일한 옵션입니다.  또는 다음 문서를 참조하십시오.  
  
-   [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [How to: Marshal Structures Using PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
 기본적으로 네이티브 및 관리되는 구조체는 메모리에 서로 다른 방식으로 배치되므로 관리\/비관리 경계를 지나 구조체를 전달하려면 데이터 무결성을 유지하기 위한 단계가 추가로 필요합니다.  
  
 이 문서에서는 네이티브 구조체에 상응하는 관리되는 구조체를 정의하는 데 필요한 과정과 결과 구조체를 관리되지 않는 함수에 전달하는 방법에 대해 설명합니다.  이 문서에서는 문자열이나 포인터를 포함하지 않는 간단한 구조체가 사용된다고 가정합니다.  blittable 형식이 아닌 상호 운용성에 대한 자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  P\/Invoke에서는 blittable이 아닌 형식을 반환 값으로 사용할 수 없습니다.  blittable 형식의 표현은 관리 코드와 비관리 코드에서 동일합니다.  자세한 내용은 [Blittable 형식 및 비 Blittable 형식](../Topic/Blittable%20and%20Non-Blittable%20Types.md)을 참조하십시오.  
  
 관리\/비관리 경계를 지나 단순한 blittable 구조체를 마샬링하려면 먼저 각 네이티브 구조체의 관리되는 버전을 정의해야 합니다.  이러한 구조체는 유효한 어떤 이름이나 사용할 수 있습니다. 두 구조체의 네이티브 버전과 관리되는 버전 사이에는 데이터 레이아웃을 제외한 어떠한 관계도 없습니다.  따라서 관리되는 버전에는 네이티브 버전과 크기 및 순서가 동일한 필드가 포함되어 있어야 합니다. 구조체의 관리되는 버전과 네이티브 버전이 동일한지 확인하는 메커니즘은 없으므로 두 버전이 호환되지 않더라도 런타임 이전에는 이 문제가 드러나지 않습니다.  두 구조체의 데이터 레이아웃을 동일하게 만드는 작업은 프로그래머가 직접 수행해야 합니다.  
  
 때로는 성능을 향상시키기 위해 관리되는 구조체의 멤버가 다시 정렬되므로 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 사용하여 구조체를 순차적으로 배치하도록 지정해야 합니다.  구조체 압축 설정을 네이티브 구조체에 사용되는 것과 동일하게 명시적으로 지정하는 것도 좋은 방법입니다. Visual C\+\+의 경우 기본적으로 두 관리 코드 모두에 대해 8바이트 구조체 압축을 사용합니다.  
  
1.  그런 다음 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 구조체를 허용하는 관리되지 않는 함수에 상응하는 진입점을 선언하고 함수 시그니처에는 구조체의 관리되는 버전을 사용합니다. 두 버전의 구조체에 동일한 이름을 사용하는 경우 이는 모의 지점으로 사용됩니다.  
  
2.  이제 관리 코드에서 관리되는 버전의 구조체를 관리되지 않는 함수에 전달할 수 있습니다. 이러한 관리되지 않는 함수는 실제로 관리되는 함수인 것처럼 간주됩니다.  이 구조체는 아래 예제에서와 같이 값이나 참조로 전달될 수 있습니다.  
  
## 예제  
 다음 코드는 관리되지 않는 모듈과 관리되는 모듈로 구성되어 있습니다.  관리되지 않는 모듈은 Location이라는 구조체와 Location 구조체의 두 인스턴스를 사용하는 GetDistance라는 함수를 정의하는 DLL입니다.  두 번째 모듈은 GetDistance 함수를 가져오고 이를 관리되는 버전의 Location 구조체인 MLocation을 사용하여 정의하는 관리되는 명령줄 응용 프로그램입니다.  실제로는 두 버전의 구조체에 모두 동일한 이름을 사용할 수 있지만 이 예제에서는 관리되는 버전을 사용하여 DllImport 프로토타입을 정의하는 방법을 보여 주기 위해 서로 다른 이름을 사용합니다.  
  
 관리되는 모듈은 \/CLR을 사용하여 컴파일되지만 \/clr:pure를 사용해도 컴파일됩니다.  
  
 DLL의 어떠한 부분도 일반적인 \#include 지시문을 사용하여 관리 코드에 노출되지 않습니다.  실제로는 런타임이 되어야 DLL에 액세스하게 되므로 DllImport를 사용하여 가져온 함수에 문제가 있더라도 컴파일할 때는 문제가 발견되지 않습니다.  
  
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
  
## 예제  
  
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
  
  **\[unmanaged\] loc1\(0,0\) loc2\(100,100\)**  
**\[managed\] distance \= 141.42135623731**  
**\[unmanaged\] Initializing location...**  
**\[managed\] x\=50 y\=50**   
## 참고 항목  
 [C\+\+에서 명시적 PInvoke 사용\(DllImport 특성\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)