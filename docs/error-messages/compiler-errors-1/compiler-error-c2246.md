---
title: "컴파일러 오류 C2246 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2246
dev_langs:
- C++
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: cef6eeb45460e4fff1c1fe5e03d8b1e97eb95d7d
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2246"></a>컴파일러 오류 C2246
'identifier': 지역으로 정의된 클래스에 잘못된 정적 데이터 멤버가 있습니다.  
  
 로컬 범위를 가진 클래스, 구조체 또는 공용 구조체의 멤버가 `static`으로 선언되었습니다.  
  
 다음 샘플에서는 C2246을 생성합니다.  
  
```  
// C2246.cpp  
// compile with: /c  
void func( void ) {  
   class A { static int i; };   // C2246  i is local to func  
   static int j;   // OK  
};  
```
