---
title: "컴파일러 오류 C3846 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 58ffd3f240505d173014f1f9b358b4957a41eaf5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3846"></a>컴파일러 오류 C3846
'symbol': 'assembly2'에서 기호를 가져올 수 없습니다: 'assembly1' 다른 어셈블리에서 'symbol' 이미 가져왔기 대로  
  
 참조 된 어셈블리에서 이전에 가져온 때문에 참조 된 어셈블리에서에 기호를 가져올 수 없습니다.  
  
## <a name="example"></a>예제
다음 샘플에서는 C3846 오류가 생성 됩니다.  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 하 고이 컴파일합니다.  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  

