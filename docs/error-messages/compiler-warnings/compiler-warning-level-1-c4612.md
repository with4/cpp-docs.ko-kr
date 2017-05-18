---
title: "컴파일러 경고 (수준 1) C4612 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: ede7b643c5be50f430859f2716e542560d6b04c5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4612"></a>컴파일러 경고(수준 1) C4612
포함 파일 이름에 오류가 있습니다.  
  
 파일 이름이 잘못되었거나 누락된 경우 **#pragma include_alias** 에서 이 경고가 발생합니다.  
  
 에 대 한 인수는 **#pragma include_alias** 문을 으로부터의 인용 צ ְ ײ (**"***filename***"**) 또는 꺾쇠 괄호 양식 (**\<***filename***>**), 있지만 둘 다 동일한 양식을 사용 해야 합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```
