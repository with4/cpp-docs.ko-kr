---
title: "컴파일러 오류 C2882 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2882
dev_langs: C++
helpviewer_keywords: C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: acbe0158dd0514df066b37ffcc7544602ce3f5ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2882"></a>컴파일러 오류 C2882
'name': 식에서 네임 스페이스 식별자를 잘못 사용 했습니다.  
  
 식에 네임 스페이스 이름을 사용 하려고 했습니다.  
  
 다음 샘플에서는 C2882 오류가 생성 됩니다.  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```