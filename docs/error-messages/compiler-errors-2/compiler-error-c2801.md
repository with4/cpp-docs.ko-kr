---
title: "컴파일러 오류 C2801 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2801
dev_langs: C++
helpviewer_keywords: C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41e7956ace6c54cd55a2ed9f68f18c867bc80ad9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2801"></a>컴파일러 오류 C2801
'operator 연산자' static이 아닌 멤버 여야 합니다.  
  
 비정적 멤버로 다음과 같은 연산자를 오버 로드할 수 있습니다.  
  
-   할당`=`  
  
-   클래스 멤버 액세스`->`  
  
-   첨자`[]`  
  
-   함수 호출`()`  
  
 가능한 C2801 원인:  
  
-   오버 로드 된 연산자가 클래스, 구조체 또는 공용 구조체 멤버.  
  
-   오버 로드 된 연산자가 선언 `static`합니다.  
  
-   다음 샘플에서는 C2801 오류가 생성 됩니다.  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```