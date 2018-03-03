---
title: "컴파일러 오류 C3280 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3280
dev_langs:
- C++
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ca68d60e5a6413d4793402d9d9ed8dfe060272e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3280"></a>컴파일러 오류 C3280
'class': 관리되는 형식의 멤버-함수는 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 관리되는 클래스 멤버 함수를 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 다음 샘플에서는 C3280을 생성합니다.  
  
```  
// C3280_2.cpp  
// compile with: /clr  
ref struct A {  
   void func();  
};  
  
#pragma managed(push,off)  
  
void A::func()   // C3280  
{  
}  
  
#pragma managed(pop)  
```  
