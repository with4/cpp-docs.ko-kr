---
title: "컴파일러 오류 C2871 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2871
dev_langs:
- C++
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 7f26c189dc1e8b22d328c6fc65c6dd825f4720d7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2871"></a>컴파일러 오류 C2871
'name':이 이름의 네임 스페이스가 없습니다.  
  
네임 스페이스에 없는 식별자를 전달 하는 경우이 오류가 발생 합니다는 [를 사용 하 여](../../cpp/namespaces-cpp.md#using_directives) 지시문입니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C2871 오류가 생성 됩니다.  
  
```cpp  
// C2871.cpp  
// compile with: /c
namespace a {
   int fn(int i) { return i; }
} 
namespace b { 
   using namespace d;   // C2871 because d is not a namespace  
   using namespace a;   // OK
}  
```
