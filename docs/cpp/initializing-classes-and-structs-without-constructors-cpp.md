---
title: (C + +) 생성자 없이 클래스 및 구조체 초기화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bca7ef417a633f186f2b7ca6f7d92af37e780420
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409338"
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>생성자 없이 클래스 및 구조체 초기화(C++)
클래스, 특히 비교적 간단한 클래스에 대해 항상 생성자를 정의할 필요는 없습니다. 사용자는 다음 예제와 같이 균일 초기화를 사용하여 클래스 또는 구조체의 개체를 초기화할 수 있습니다.  
  
```cpp 
#include "stdafx.h"  
#include <Windows.h>  
  
// No constructor  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
// Has a constructor  
struct TempData2  
{  
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :  
       minTemp(minimum), maxTemp(maximum), current(cur), stationId(id), time(t) {}  
    int stationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
int main()  
{  
    // Member initialization (in order of declaration):  
    TempData td{ 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default{};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;  
  
    // Member declaration (in order of ctor parameters)  
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, GetCurrentTime() };  
  
    return 0;  
}  
```  
  
 클래스 또는 구조체에 생성자가 없는 경우 제공 하는 멤버 클래스에서 선언 되는 순서로 목록 요소를 참고 합니다. 클래스에 생성자가 하는 경우 매개 변수를 순서 대로 요소를 제공 합니다.  
  
## <a name="see-also"></a>참고자료  
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)   
 [생성자](../cpp/constructors-cpp.md)