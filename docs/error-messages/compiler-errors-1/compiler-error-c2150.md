---
title: "컴파일러 오류 C2150 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2150
dev_langs:
- C++
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
caps.latest.revision: 9
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
ms.openlocfilehash: 16e080e549ce436573a5d73d743ed6ac771223c2
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2150"></a>컴파일러 오류 C2150
'identifier': 비트 필드의 형식은 'int', 'signed int' 또는 'unsigned int'이어야 합니다.  
  
 비트 필드 수 하는 데 필요한 `int`, `signed``int`, 또는 `unsigned``int`합니다.  
  
 다음 샘플에서는 C2150을 생성합니다.  
  
```  
// C2150.cpp  
// compile with: /c  
struct A {  
   float a : 8;    // C2150  
   int i : 8;   // OK  
};  
```
