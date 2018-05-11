---
title: 컴파일러 경고 (수준 4) C4706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1131147a9600525746cb3e89119189ed9e5026a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4706"></a>컴파일러 경고(수준 4) C4706
조건식 내에서 할당  
  
 조건식의 테스트 값은 할당의 결과임 합니다.  
  
 합법적으로 테스트 식을 포함 하는 다른 식에 사용할 수 있는 값 (할당의 왼쪽에 값)이 있습니다.  
  
 다음 샘플에서는 C4706 오류가 생성 됩니다.  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 테스트 조건 주위에 괄호를 두 번 하는 경우에 경고가 발생 합니다.  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 의도 라면와 관계를 테스트 하 고 사용 하도록 할당을 설정 하지는 `==` 연산자입니다. 예를 들어 다음 줄에서는 테스트 여부는 고 b가 같은 경우:  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 테스트는 할당의 결과 값을 확인 하려는 경우 할당 된 0이 아닌 값 또는 null이 아닌 확인을 테스트 합니다. 예를 들어 다음 코드는이 경고를 생성 하지 않습니다.  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```