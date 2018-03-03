---
title: "컴파일러 경고 (수준 4) C4100 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4100
dev_langs:
- C++
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72236ee0c100388906689121a0936daf23c58e89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4100"></a>컴파일러 경고(수준 4) C4100
'identifier': 참조 되지 않은 형식 매개 변수  
  
 형식 매개 변수는 함수의 본문에서 참조 하지 않습니다. 참조 되지 않은 매개 변수는 무시 됩니다.  
  
 코드에서 소멸자를 호출할 때 C4100 발급할 수도 있습니다는 참조 되지 않는 기본 형식의 매개 변수입니다.  Visual c + + 컴파일러의 제한 사항입니다.  
  
 다음 샘플에서는 C4100 오류가 생성 됩니다.  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```