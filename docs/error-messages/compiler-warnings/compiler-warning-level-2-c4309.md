---
title: "컴파일러 경고 (수준 2) C4309 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4309
dev_langs: C++
helpviewer_keywords: C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43d4da7be0fa4e37cb87524b8e165800f21d1855
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4309"></a>컴파일러 경고(수준 2) C4309
'conversion': 상수 값 잘림  
  
 형식 변환으로 할당 된 공간을 초과 하는 상수입니다. 상수에 대해 더 큰 형식을 사용 해야 합니다.  
  
 다음 샘플에서는 C4309 오류가 생성 됩니다.  
  
```  
// C4309.cpp  
// compile with: /W2  
int main()  
{  
   char c = 128;   // C4309  
}  
```