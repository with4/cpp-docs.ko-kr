---
title: 배열 초기화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1ecb15cfc34ec518f46474497a3577a51b00c4e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408958"
---
# <a name="initializing-arrays"></a>배열 초기화
클래스에 생성자가 있으면 해당 클래스의 배열은 생성자에 의해 초기화됩니다. 이니셜라이저 목록의 항목 수가 배열의 요소 수보다 적은 경우 나머지 요소에 대해 기본 생성자가 사용됩니다. 클래스에 정의된 기본 생성자가 없는 경우 이니셜라이저 목록이 완전해야 합니다. 즉, 배열의 각 요소에 하나의 이니셜라이저가 있어야 합니다.  
  
 생성자 두 개를 정의하는 `Point` 클래스를 살펴보세요.  
  
```cpp 
// initializing_arrays1.cpp  
class Point  
{  
public:  
   Point()   // Default constructor.  
   {  
   }  
   Point( int, int )   // Construct from two ints  
   {  
   }  
};  
  
// An array of Point objects can be declared as follows:  
Point aPoint[3] = {  
   Point( 3, 3 )     // Use int, int constructor.  
};  
  
int main()  
{  
}  
```  
  
 `aPoint`의 첫 번째 요소는 `Point( int, int )` 생성자를 사용하여 생성되고 나머지 두 요소는 기본 생성자를 사용하여 생성됩니다.  
  
 정적 멤버 배열 (여부 **const** 여부) (외부 클래스 선언) 해당 정의에서 초기화할 수 있습니다. 예를 들어:  
  
```cpp 
// initializing_arrays2.cpp  
class WindowColors  
{  
public:  
    static const char *rgszWindowPartList[7];  
};  
  
const char *WindowColors::rgszWindowPartList[7] = {  
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",  
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };  
int main()  
{  
}  
```  