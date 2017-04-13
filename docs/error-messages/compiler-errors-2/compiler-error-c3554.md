---
title: "컴파일러 오류 C3554 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3554
dev_langs:
- C++
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
caps.latest.revision: 4
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
ms.openlocfilehash: 29fdf7dacbc24f136d24b283c787d40891969678
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3554"></a>컴파일러 오류 C3554
'decltype'을 다른 형식 지정자와 함께 사용할 수 없습니다.  
  
 형식 지정자로 `decltype()` 키워드를 한정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3554 오류를 생성합니다.  
  
```  
int x;  
unsigned decltype(x); // C3554  
```
