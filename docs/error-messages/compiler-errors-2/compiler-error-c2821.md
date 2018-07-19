---
title: 컴파일러 오류 C2821 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2821
dev_langs:
- C++
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8c134d84ef27110cde83d54cbb8e46aa6a39efa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236561"
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