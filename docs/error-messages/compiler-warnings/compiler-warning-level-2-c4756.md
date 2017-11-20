---
title: "컴파일러 경고 (수준 2) C4756 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4756
dev_langs: C++
helpviewer_keywords: C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ead332970500afbc69e21a5ed5d6507dec571244
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4756"></a>컴파일러 경고(수준 2) C4756
상수 산술 연산에서 오버플로가 발생 했습니다.  
  
 컴파일러는 컴파일하는 동안 상수 산술 연산 수행 하는 동안 예외를 생성 합니다.  
  
 다음 샘플에서는 C4756 오류가 생성 됩니다.  
  
```  
// C4756.cpp  
// compile with: /W2 /Od  
int main()  
{  
   float f = 1e100+1e100;   // C4756  
}  
```