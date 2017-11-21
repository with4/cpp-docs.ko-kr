---
title: "컴파일러 오류 C2677 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2677
dev_langs: C++
helpviewer_keywords: C2677
ms.assetid: 76bc0b65-f52a-45a6-b6d6-0555f89da9a8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4362fdb85c6700c9f9592b9bbf626738e6c4d4b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2677"></a>컴파일러 오류 C2677
이항 'operator': 전역 연산자 ' type'를 사용 하는 발견 (또는 허용 가능한 변환이 없는)  
  
 연산자를 사용하려면 지정된 형식에 대해 오버로드하거나 연산자가 정의된 형식으로의 변환을 정의해야 합니다.  
  
 다음 샘플에서는 C2677 오류가 생성 됩니다.  
  
```  
// C2677.cpp  
class C {  
public:  
   C(){}  
} c;  
  
class D {  
public:  
   D(){}  
   operator int(){return 0;}  
} d;  
  
int main() {  
   int i = 1 >> c;   // C2677  
   int j = 1 >> d;   // OK operator int() defined  
}  
```