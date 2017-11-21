---
title: "컴파일러 오류 C2663 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2663
dev_langs: C++
helpviewer_keywords: C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a9efe20b4a80b9ff6f337d32acd35320125008dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2663"></a>컴파일러 오류 C2663
'function': 숫자 오버 로드에는 'this'이 포인터에 대 한 법적 변환이  
  
 컴파일러가 변환 하지 못했습니다 `this` 를 멤버 함수 오버 로드 된 버전입니다.  
  
 비-를 호출 하 여이 오류가 발생할 수 있습니다`const` 에 멤버 함수는 `const` 개체입니다.  가능한 해결 방법:  
  
1.  제거는 `const` 개체 선언에서 합니다.  
  
2.  추가 `const` 멤버 함수 오버 로드 중 하나에 있습니다.  
  
 다음 샘플에서는 C2663 오류가 생성 됩니다.  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```