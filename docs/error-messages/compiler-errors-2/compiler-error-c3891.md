---
title: "컴파일러 오류 C3891 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3891
dev_langs: C++
helpviewer_keywords: C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: daf8c50dfb041194e376b1b62943da021a423ed4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3891"></a>컴파일러 오류 C3891
'var': 리터럴 데이터 멤버는 l-value로 사용할 수 없습니다  
  
 A [리터럴](../../windows/literal-cpp-component-extensions.md) 변수는 const 및 선언에 초기화 한 후 해당 값을 변경할 수 없습니다.  
  
 다음 샘플에서는 C3891 오류가 생성 됩니다.  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```