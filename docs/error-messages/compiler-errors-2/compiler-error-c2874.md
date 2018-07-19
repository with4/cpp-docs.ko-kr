---
title: 컴파일러 오류 C2874 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2874
dev_langs:
- C++
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aebe8054c68e1474a2597da5bda7bb985eb205dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243289"
---
# <a name="compiler-error-c2874"></a>컴파일러 오류 C2874
사용 하 여 선언 하면 'symbol'의 여러 선언  
  
 이 선언은 동일 항목을 두 번 정의 됩니다.  
  
 다음 샘플에서는 C2874 오류가 생성 됩니다.  
  
```  
// C2874.cpp  
namespace Z {  
   int i;  
}  
  
int main() {  
   int i;  
   using Z::i;   // C2874, i already declared  
}  
```