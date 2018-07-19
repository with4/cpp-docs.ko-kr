---
title: 컴파일러 오류 C2705 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2705
dev_langs:
- C++
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dce6bdb0a5c20fbe54b04eaf83ee8f90427017c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235457"
---
# <a name="compiler-error-c2705"></a>컴파일러 오류 C2705
'label': '예외 처리기 블록' 범위로 잘못 점프 했습니다  
  
 실행이 내의 레이블로 이동는 `try` / `catch`, `__try` / `__except`, `__try` / `__finally` 블록입니다. 자세한 내용은 [예외 처리](../../cpp/exception-handling-in-visual-cpp.md)를 참조하세요.  
  
 다음 샘플에서는 C2705 오류가 생성 됩니다.  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```