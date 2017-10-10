---
title: "컴파일러 오류 C2581 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2581
dev_langs:
- C++
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 205d972237a71a05839dbc4236d248a11e6ee53d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2581"></a>컴파일러 오류 C2581
'type': 정적 ' operator =' 함수가 잘못 되었습니다.  
  
 할당 (`=`) 연산자가 잘못 선언 되었습니다로 `static`합니다. 대입 연산자가 될 수 없습니다 `static`합니다. 자세한 내용은 참조 [사용자 정의 연산자 (C + + /cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2581 오류가 발생 합니다.  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```
