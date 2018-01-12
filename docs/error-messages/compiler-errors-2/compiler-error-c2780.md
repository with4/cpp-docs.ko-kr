---
title: "컴파일러 오류 c 2780 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2780
dev_langs: C++
helpviewer_keywords: C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8acea179c73b5a4821f2c13645b594c71413e426
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2780"></a>컴파일러 오류 c 2780
'declaration' : 인수가 N개 있어야 하는데 M개를 사용했습니다.  
  
 함수 템플릿에 인수가 너무 적거나 너무 많습니다.  
  
 다음 샘플에서는 C2780을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2780.cpp  
template<typename T>  
void f(T, T){}  
  
int main() {  
   f(1);  // C2780  
   // try the following line instead  
   // f(1,2);  
}  
```