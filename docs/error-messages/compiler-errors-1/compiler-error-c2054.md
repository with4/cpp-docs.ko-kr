---
title: "컴파일러 오류 C2054 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2054
dev_langs:
- C++
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1ab12a8395f3587f0fbdca5ad821cd9ec2241d25
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2054"></a>컴파일러 오류 C2054
예상 ' (' 'identifier'를 수행 하려면  
  
 함수 식별자는 닫는 괄호가 필요한 컨텍스트에서 사용 됩니다.  
  
 이 오류는 복잡 한 초기화에 등호 (=)를 생략 하 여 발생할 수 있습니다.  
  
 다음 샘플에서는 C2054 오류가 생성 됩니다.  
  
```  
// C2054.c  
int array1[] { 1, 2, 3 };   // C2054, missing =  
```  
  
 해결 방법:  
  
```  
// C2054b.c  
int main() {  
   int array2[] = { 1, 2, 3 };  
}  
```
