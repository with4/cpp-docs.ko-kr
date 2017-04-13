---
title: "컴파일러 오류 C2013 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2013
dev_langs:
- C++
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
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
ms.openlocfilehash: 78c41fa998b7ef229ccdaccd6cfa0336af7a8632
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2013"></a>컴파일러 오류 C2013
'>'가 없습니다.  
  
 `#include` 지시문에 닫는 꺾쇠 괄호가 없습니다. 오류를 해결하려면 닫는 대괄호를 추가합니다.  
  
 다음 샘플에서는 C2013을 생성합니다.  
  
```  
// C2013.cpp  
#include <stdio.h    // C2013  
```  
  
 해결 방법:  
  
```  
// C2013b.cpp  
// compile with: /c  
#include <stdio.h>  
```
