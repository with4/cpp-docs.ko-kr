---
title: "컴파일러 오류 C2229 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2229
dev_langs: C++
helpviewer_keywords: C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c54e3affb39cb396df1caaafe6450d5c6ac80f6e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2229"></a>컴파일러 오류 C2229
'identifier' 형식에 잘못 된 크기가 0 인 배열  
  
 구조 또는 비트 필드의 멤버는 크기가 0 인 배열 마지막 멤버를 포함 합니다.  
  
 구조체의 마지막 멤버로 크기는 0 배열을 있을 수 있지만, 때문에 구조체를 할당할 때 해당 크기를 지정 해야 합니다.  
  
 0 크기의 배열이 구조체의 마지막 구성원 없으면 컴파일러가 나머지 필드에 대 한 오프셋을 계산할 수 없습니다.  
  
 다음 샘플에서는 C2229 오류가 생성 됩니다.  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```