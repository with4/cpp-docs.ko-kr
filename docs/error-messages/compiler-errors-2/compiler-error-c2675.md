---
title: 컴파일러 오류 C2675 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb949f5d6ab5881b911bab89150ae13f47443fcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235671"
---
# <a name="compiler-error-c2675"></a>컴파일러 오류 C2675
단항 'operator': 'type' 정의 하지 않습니다이 연산자 또는 허용 되는 형식으로의 변환을 미리 정의 된 연산자  
  
 C2675는 단항 연산자를 사용 하는 경우에 발생할 수 있습니다 하며 형식을 정의 하지 않습니다 연산자나 허용 되는 형식으로의 변환을 미리 정의 된 운영자에 게 있습니다. 연산자를 사용하려면 지정된 형식에 대해 오버로드하거나 연산자가 정의된 형식으로의 변환을 정의해야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2675 오류가 발생 합니다.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```