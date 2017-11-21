---
title: "컴파일러 오류 C2993 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2993
dev_langs: C++
helpviewer_keywords: C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6306b2c3c632d25ee6b37a025516f759cc126a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2993"></a>컴파일러 오류 C2993
'identifier': 비형식 템플릿 매개 변수 'parameter'에 대 한 형식이 잘못 되었습니다.  
  
 구조체 또는 공용 구조체 인수가 있는 템플릿을 선언할 수 없습니다. 포인터를 사용 하 여 구조체 및 공용 구조체를 템플릿 매개 변수로 전달 합니다.  
  
 다음 샘플에서는 C2993 오류가 생성 됩니다.  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 이 오류는 Visual Studio.NET 2003 컴파일러 규칙 작업의 결과로 생성 됩니다: 부동 소수점 비형식 템플릿 매개 변수를 더 이상 허용 합니다. C + + 표준 부동 소수점 비형식 템플릿 매개 변수 허용 하지 않습니다.  
  
 함수 템플릿이 면 부동 전달에 대 한 함수 인수를 사용 하 여 (이 코드는 Visual c + +의 Visual Studio.NET 2003 및 Visual Studio.NET 버전에서 사용할 수 있습니다) 비형식 템플릿 매개 변수를 가리킵니다. 클래스 템플릿인지 경우 쉽게 해결 방법이 없습니다.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```