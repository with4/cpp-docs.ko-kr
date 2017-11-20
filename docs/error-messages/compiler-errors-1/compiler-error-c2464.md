---
title: "컴파일러 오류 C2464 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2464
dev_langs: C++
helpviewer_keywords: C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7e2600608ae490363d9042ad72ad91bf7cfe32d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2464"></a>컴파일러 오류 C2464
'identifier': 'n e w'에 대 한 참조를 할당 합니다. 사용할 수 없습니다  
  
 할당 된 참조 식별자는 `new` 연산자입니다. 참조는 하므로 메모리 개체가 아니므로 `new` 에 대 한 포인터를 반환할 수 없습니다. 표준 변수 선언 구문을 사용 하 여 참조를 선언 합니다.  
  
 다음 샘플에서는 C2464 오류가 생성 됩니다.  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```