---
title: "컴파일러 오류 C2614 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2614
dev_langs: C++
helpviewer_keywords: C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 077762fef5474b3761c504224c58de83d82bdb12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2614"></a>컴파일러 오류 C2614
'class1': 멤버 초기화가 잘못: 'class2'은 기본 또는 멤버  
  
 멤버 또는 기본 클래스는 클래스 또는 구조체에 대 한 초기화 목록에 나타날 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2614 오류가 발생 합니다.  
  
```  
// C2614.cpp  
// compile with: /c  
struct A {  
   int i;  
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A  
};  
  
struct A2 {  
   int B;  
   int i;  
   A2( int ia ) : B( i ) {};   // OK  
};  
```