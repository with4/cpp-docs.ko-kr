---
title: 컴파일러 경고 (수준 1) C4144 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4144
dev_langs:
- C++
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b84e8a062871bfaa1d83da50175e3485f2d8bd2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281341"
---
# <a name="compiler-warning-level-1-c4144"></a>컴파일러 경고 (수준 1) C4144
'expression': 관계식을 switch 식  
  
 지정한 관계식의 제어 식으로 사용 되었습니다는 [전환](../../cpp/switch-statement-cpp.md) 문. 관련 된 case 문에 부울 값이 제공 됩니다. 다음 샘플에서는 C4144 오류가 생성 됩니다.  
  
```  
// C4144.cpp  
// compile with: /W1  
int main()  
{  
   int i = 0;  
   switch(!i) {   // C4144, remove the ! to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```