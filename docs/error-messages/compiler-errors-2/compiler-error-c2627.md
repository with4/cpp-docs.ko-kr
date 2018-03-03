---
title: "컴파일러 오류 C2627 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2627
dev_langs:
- C++
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f72850dc11fb013c385cf2e4414f758230c0923e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2627"></a>컴파일러 오류 C2627
'function': 멤버 함수를 익명 공용 구조체에 사용할 수 없습니다  
  
 [익명 공용 구조체](../../cpp/unions.md#anonymous_unions) 멤버 함수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2627 오류가 생성 됩니다.  
  
```  
// C2627.cpp  
int main() {  
   union { void f(){} };   // C2627  
   union X { void f(){} };  
}  
```