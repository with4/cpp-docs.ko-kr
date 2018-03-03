---
title: "배열 초기화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 42d47f8ba7f7df8285d3c4f685a212c77974b144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-arrays"></a>배열 초기화
클래스에 생성자가 있으면 해당 클래스의 배열은 생성자에 의해 초기화됩니다. 이니셜라이저 목록의 항목 수가 배열의 요소 수보다 적은 경우 나머지 요소에 대해 기본 생성자가 사용됩니다. 클래스에 정의된 기본 생성자가 없는 경우 이니셜라이저 목록이 완전해야 합니다. 즉, 배열의 각 요소에 하나의 이니셜라이저가 있어야 합니다.  
  
 생성자 두 개를 정의하는 `Point` 클래스를 살펴보세요.  
  
```  
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
  
 정적 멤버 배열 (여부 **const** 또는 not) (외부 클래스 선언) 해당 정의에서 초기화할 수 있습니다. 예:  
  
```  
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
  
