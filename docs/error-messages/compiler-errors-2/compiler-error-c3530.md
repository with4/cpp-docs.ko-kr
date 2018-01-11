---
title: "컴파일러 오류 C3530 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3530
dev_langs: C++
helpviewer_keywords: C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a71820e6303c67e3d247c7da6dddc184e5cb41a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3530"></a>컴파일러 오류 C3530
'auto' 다른 형식 지정자와 함께 사용할 수 없습니다.  
  
 형식 지정자와 함께 사용 됩니다는 `auto` 키워드입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  사용 하는 변수 선언에 형식 지정자를 사용 하지 마십시오는 `auto` 키워드입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 때문에 c 3530 변수 `x` 함께 선언 되는 `auto` 키워드 및 형식 `int`, 때문이 예제에서는 컴파일된 **/zc: auto**합니다.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)