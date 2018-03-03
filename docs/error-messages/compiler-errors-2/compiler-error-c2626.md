---
title: "컴파일러 오류 C2626 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2626
dev_langs:
- C++
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 837fae0a32d473b5bf9adcf5c5fd4c564c7b033a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2626"></a>컴파일러 오류 C2626
'identifier': 익명 구조체 또는 공용 구조체에서는 전용 또는 보호된 데이터 멤버가 허용되지 않습니다.  
  
 익명 구조체 또는 공용 구조체의 멤버는 공용 액세스 권한이 있어야 합니다.  
  
 다음 샘플에서는 C2626을 생성합니다.  
  
```  
// C2626.cpp  
int main() {  
   union {  
   protected:  
      int j;     // C2626, j is protected  
   private:  
      int k;     // C2626, k is private  
   };  
}  
```  
  
 이 문제를 해결하려면 전용 또는 보호된 태그를 제거하세요.  
  
```  
// C2626b.cpp  
int main() {  
   union {  
   public:  
      int i;   // OK, i is public  
   };  
}  
```