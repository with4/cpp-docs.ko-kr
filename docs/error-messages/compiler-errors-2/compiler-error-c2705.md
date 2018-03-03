---
title: "컴파일러 오류 C2705 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2705
dev_langs:
- C++
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4aa9cb8574675763b9e51e0409b61dc09e3ab810
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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