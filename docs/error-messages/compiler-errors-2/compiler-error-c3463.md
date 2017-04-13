---
title: "컴파일러 오류 C3463 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3463
dev_langs:
- C++
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f1d148a21e532863315470366820cc825c45f782
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3463"></a>컴파일러 오류 C3463
'type': 형식을 'implements' 특성에 사용할 수 없습니다.  
  
 에 전달 된 값이 잘못 된 [구현](../../windows/implements-cpp.md) 특성입니다. 예를 들어 `implements`에 인터페이스를 전달할 수 있지만 포인터를 인터페이스에 전달할 수는 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3463을 생성합니다.  
  
```  
// C3463.cpp  
// compile with: /c  
#include <windows.h>  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X {};  
  
typedef X* PX;  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463  
// try the following line instead  
// [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ]  
class CMyClass : public X {};  
```
