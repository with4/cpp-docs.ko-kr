---
title: "컴파일러 오류 C3489 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3489
dev_langs:
- C++
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4605b0b688cc879f68224442e7df5571cb8d2f7d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3489"></a>컴파일러 오류 C3489
기본 캡처 모드가 값 방식인 경우 'var'이 필요합니다.  
  
 람다 식에 대한 기본 캡처 모드를 값 방식으로 지정할 경우 해당 식의 캡처 절에 변수를 값으로 전달할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   변수를 캡처 절에 명시적으로 전달하지 마세요. 또는  
  
-   값 방식을 기본 캡처 모드로 지정하지 마세요. 또는  
  
-   참조 방식을 기본 캡처 모드로 지정합니다. 또는  
  
-   변수를 캡처 절에 참조로 전달합니다. 이 경우 람다 식의 동작이 변경될 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 모드가 값 방식인 람다 식의 캡처 절에 `n` 변수가 값으로 나타나기 때문에 C3489를 생성합니다.  
  
```  
// C3489a.cpp  
  
int main()  
{  
   int n = 5;  
   [=, n]() { return n; } (); // C3489  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 C3489에 대한 네 가지 해결 방법을 보여 줍니다.  
  
```  
// C3489b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass n to the capture clause.  
   [=]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-value as the default capture mode.  
   [n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-reference as the default capture mode.  
   [&, n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by reference to the capture clause.  
   [&n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)
