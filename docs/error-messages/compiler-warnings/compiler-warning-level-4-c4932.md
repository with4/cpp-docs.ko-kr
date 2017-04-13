---
title: "컴파일러 경고 (수준 4) C4932 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4932
dev_langs:
- C++
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
caps.latest.revision: 9
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
ms.openlocfilehash: 6b479121e325035a2bf90bd239812613b73343ea
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4932"></a>컴파일러 경고(수준 4) C4932
__identifier (identifier) 및 \__identifier(identifier) 서로 구분 되지 않으므로  
  
 컴파일러에서 구분할 수 없는 **_finally** 및 `__finally` 또는 `__try` 및 **_try** 에 전달 된 매개 변수 [__identifier](../../windows/identifier-cpp-cli.md)합니다. 균형이 깨어 집니다 대로 모두 동일한 프로그램에서 식별자로 사용를 시도 하지 않아야는 [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) 오류입니다.  
  
 다음 샘플에서는 C4932를 생성합니다.  
  
```  
// C4932.cpp  
// compile with: /clr /W4 /WX  
int main() {  
   int __identifier(_finally) = 245;   // C4932  
   int __identifier(__finally) = 25;   // C4932  
}  
```
