---
title: "컴파일러 경고 (수준 1) C4804 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4804
dev_langs: C++
helpviewer_keywords: C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 95a96844406bb803c46bd4f1b0162be711105394
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4804"></a>컴파일러 경고(수준 1) C4804
'operation': 안전 하지 않은 작업에 사용 되는 ' bool' 형식 사용  
  
 이 경고는 사용 하는 `bool` 변수 또는 예기치 않은 방식으로 값입니다. 예를 들어 C4804 음수 단항 연산자와 같은 연산자를 사용 하는 경우 생성 됩니다 (**-**) 또는 보수 연산자 (`~`). 컴파일러는 식을 계산합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4804 오류가 생성 됩니다.  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```