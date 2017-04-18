---
title: "컴파일러 경고 (수준 4) C4960 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4960
dev_langs:
- C++
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
caps.latest.revision: 8
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
ms.openlocfilehash: c61350cebf8601d706e7efec9273c967008bd6fd
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4960"></a>컴파일러 경고(수준 4) C4960
'function'이 너무 커서 프로파일링할 수 없습니다.  
  
 사용 하는 경우 [/ltcg: pgoptimize](../../build/reference/ltcg-link-time-code-generation.md), 컴파일러 65, 535 명령 보다 큰 함수를 포함 하는 입력된 모듈을 발견 했습니다. 이렇게 큰 함수는 프로필 기반 최적화에 사용할 수 없습니다.  
  
 이 경고를 해결하려면 함수 크기를 줄입니다.
