---
title: "컴파일러 경고 (수준 4) C4918 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4918
dev_langs:
- C++
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
caps.latest.revision: 7
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
ms.openlocfilehash: ec8c01dc780b8f7ad5d3f10cfd8dea890fb64f70
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4918"></a>컴파일러 경고(수준 4) C4918
'character': pragma 최적화 목록에 잘못된 문자가 있습니다.  
  
 최적화 목록에 알 수 없는 문자를 찾을 수는 [최적화](../../preprocessor/optimize.md) pragma 문의 합니다.  
  
 예를 들어 다음 문은 C4918을 생성합니다.  
  
```  
// C4918.cpp  
// compile with: /W4  
#pragma optimize("X", on) // C4918 expected  
int main()  
{  
}  
```
