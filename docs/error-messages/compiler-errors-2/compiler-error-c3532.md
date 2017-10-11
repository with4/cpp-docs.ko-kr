---
title: "컴파일러 오류 C3532 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3532
dev_langs:
- C++
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e78db21d00ea93378358a1147163276fb12bdfd5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3532"></a>컴파일러 오류 C3532
'type': 'auto'의 잘못 된 사용  
  
 표시 된 형식으로 선언할 수 없습니다는 `auto` 키워드입니다. 예를 들어 사용할 수 없습니다는 `auto` 배열 또는 메서드를 선언 하려면 키워드 형식을 반환 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  초기화 식의 유효한 형식이 있는지 확인 합니다.  
  
2.  배열 또는 메서드 반환 형식을 선언 하지 않으면 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 C3532 때문에 `auto` 키워드 메서드 반환 형식을 선언할 수 없습니다.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 C3532 때문에 `auto` 키워드 배열을 선언할 수 없습니다.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)
