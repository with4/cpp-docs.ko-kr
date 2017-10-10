---
title: "컴파일러 오류 C2094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2094
dev_langs:
- C++
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f20930a38a429aba3e3959f57f937bbfa9962da9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2094"></a>컴파일러 오류 C2094
'identifier' 레이블이 정의되지 않았습니다.  
  
[goto](../../cpp/goto-statement-cpp.md) 문에서 사용하는 레이블이 함수에 존재하지 않습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C2094를 생성합니다.  
  
```cpp  
// C2094.c  
int main() {  
   goto test;  
}   // C2094  
```  
  
 해결 방법:  
  
```cpp  
// C2094b.c  
int main() {  
   goto test;  
   test:   
   {  
   }  
}  
```
