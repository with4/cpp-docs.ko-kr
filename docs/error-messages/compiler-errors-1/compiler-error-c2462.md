---
title: "컴파일러 오류 C2462 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2462
dev_langs: C++
helpviewer_keywords: C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af4b7e303a67ed1eae3d217964818d1b4cd05b96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2462"></a>컴파일러 오류 C2462
'identifier': ' new-expression '에서 형식을 정의할 수 없습니다  
  
 피연산자 필드에는 형식을 정의할 수 없습니다는 `new` 연산자입니다. 형식 정을 별도의 문으로 넣습니다.  
  
 다음 샘플에서는 C2462 오류가 생성 됩니다.  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```