---
title: "컴파일러 오류 C3890 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3890
dev_langs: C++
helpviewer_keywords: C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3f98846bc8a361bd03d453f2115e2063f37423f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3890"></a>컴파일러 오류 C3890
'var': 리터럴 데이터 멤버의 주소를 가져올 수 없습니다  
  
 가비지 수집 힙에 리터럴 데이터 멤버가 있습니다.  있으므로 주소 보다 유용한 경우가 가비지 수집 힙에 있는 개체를 이동할 수 있습니다.  
  
 다음 샘플에서는 C3890 오류가 생성 됩니다.  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```