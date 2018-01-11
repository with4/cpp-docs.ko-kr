---
title: "컴파일러 오류 C2781 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2781
dev_langs: C++
helpviewer_keywords: C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c9e86968cc53e5a3db8411b5557460511ac4a3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2781"></a>컴파일러 오류 C2781
'declaration': 적어도 value1 인수-value2 제공  
  
 가변 매개 변수 목록 사용 하 여 함수 템플릿에 인수가 너무 적습니다.  
  
 다음 샘플에서는 C2781 오류가 생성 됩니다.  
  
```  
// C2781.cpp  
template<typename T>  
void f(T, T, ...){}  
  
int main() {  
   f(1);   // C2781  
  
   // try the following line instead  
   f(1,1);  
}  
```