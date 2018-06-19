---
title: 컴파일러 오류 C3640 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3640
dev_langs:
- C++
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8ec2e22033ea4cc1b475ab1f838bb77d96916e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267188"
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