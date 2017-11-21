---
title: "컴파일러 오류 C2556 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2556
dev_langs: C++
helpviewer_keywords: C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6678c34022c28dccfa5920809e7b8d6db0d39546
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2556"></a>컴파일러 오류 C2556
'identifier': 오버 로드 된 함수의 반환 형식 그만 다릅니다.  
  
 오버 로드 된 함수 반환 형식은 각기 다르지만 동일한 매개 변수 목록을 갖고 있습니다. 각 오버 로드 된 함수에는 고유한 형식 매개 변수 목록이 있어야 합니다.  
  
 다음 샘플에서는 C2556 오류가 생성 됩니다.  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```