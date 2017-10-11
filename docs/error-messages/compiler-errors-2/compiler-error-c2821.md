---
title: "컴파일러 오류 C2821 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2821
dev_langs:
- C++
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f0218061b8d34eca00baa5834053d90711798bd0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2821"></a>컴파일러 오류 C2821
'operator new' 첫 번째 형식 매개 변수 'unsigned int' 이어야 합니다.  
  
첫 번째 형식 매개 변수는 [new 연산자](../../standard-library/new-operators.md#op_new) 서명 되지 않은 여야 `int`합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2821 오류가 생성 됩니다.  
  
```cpp  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```
