---
title: 컴파일러 오류 C2203 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2203
dev_langs:
- C++
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0cbf64e673c84a60c37bce3ffd51bc7016eb7a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169935"
---
# <a name="compiler-error-c2203"></a>컴파일러 오류 C2203
delete 연산자는 배열의 범위를 지정할 수 없습니다  
  
 와 **/Za** (ANSI) 옵션은 `delete` 운영자 배열 전체 되지만 파트 나 배열의 특정 멤버를 삭제할 수 있습니다.  
  
 다음 샘플에서는 C2203 오류가 생성 됩니다.  
  
```  
// C2203.cpp  
// compile with: /Za  
int main() {  
   int *ar = new int[10];  
   delete [4] ar;   // C2203  
   // try the following line instead  
   // delete [] ar;  
}  
```