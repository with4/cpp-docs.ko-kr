---
title: "컴파일러 오류 C3539 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 03283217be6aabbf216e2e60ad47abfc01a961d6
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3539"></a>컴파일러 오류 C3539
'type': 템플릿 인수 'auto' 포함 된 형식일 수 없습니다.  
  
 지정 된 템플릿 인수 형식이의 사용할 수 없습니다는 `auto` 키워드입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  템플릿 인수를 지정 하지 않으면는 `auto` 키워드입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 C3539를 생성합니다.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)
