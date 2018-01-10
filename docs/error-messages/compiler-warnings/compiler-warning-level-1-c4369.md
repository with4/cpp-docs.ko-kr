---
title: "컴파일러 경고 (수준 1) C4369 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4369
dev_langs: C++
helpviewer_keywords: C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c0419908ed7d914196cd65d07a3fb43a16d75ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4369"></a>컴파일러 경고(수준 1) C4369
'열거자': 열거자 값 'value'는 'type'로 나타낼 수 없습니다, 값은 'new_value'  
  
 열거자는 지정된 된 내부 형식에 대 한 최대값 보다 클 수를 계산 했습니다.  이 중 오버플로가 발생 사이 컴파일러에 열거자 값 형식에 대해 가능한 가장 낮은 값입니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4369 경고가 발생 합니다.  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```