---
title: "컴파일러 경고 (수준 1) C4085 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4085
dev_langs:
- C++
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
caps.latest.revision: 5
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
ms.openlocfilehash: 72f27e08b97d21dd26bdd38f0d5fa4eb6c21dddb
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4085"></a>컴파일러 경고(수준 1) C4085
pragma 매개 변수는 'on' 또는 'off'이어야 합니다.  
  
 pragma에 **on** 또는 **off** 매개 변수가 필요합니다. pragma가 무시됩니다.  
  
 다음 샘플에서는 C4085를 생성합니다.  
  
```  
// C4085.cpp  
// compile with: /W1 /LD  
#pragma optimize( "t", maybe )  // C4085  
```
