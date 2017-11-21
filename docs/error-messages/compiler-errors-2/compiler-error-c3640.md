---
title: "컴파일러 오류 C3640 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3640
dev_langs: C++
helpviewer_keywords: C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 493206e55be18d1e7cc00fec55dd2e111ad5026f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3640"></a>컴파일러 오류 C3640
'member': 지역 클래스는 참조 또는 가상 멤버 함수를 정의 해야 합니다  
  
 컴파일러에는 특정 함수를 정의할 수 필요 합니다.  
  
 다음 샘플에서는 C3640 오류가 생성 됩니다.  
  
```  
// C3640.cpp  
void f()   
{  
   struct S  
   {  
      virtual void f1();   // C3640  
      // Try the following line instead:  
      // virtual void f1(){}  
   };  
}  
```