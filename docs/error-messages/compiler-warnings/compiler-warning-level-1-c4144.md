---
title: "컴파일러 경고 (수준 1) C4144 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4144
dev_langs: C++
helpviewer_keywords: C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d085cfdb4b84f6972dd42d83a94731ff56bfc2ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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