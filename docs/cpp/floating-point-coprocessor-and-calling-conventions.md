---
title: "부동 소수점 보조 프로세서 및 호출 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6d14f7f445064316c83b31e9b4cdc421d68d7255
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>부동 소수점 보조 프로세서 및 호출 규칙
부동 유지 해야 하는 경우를 작성 하는 어셈블리 루틴은 부동 소수점 보조 프로세서 반환 하지 않으면 보조 프로세서 스택을 정리 하 고 소수점 제어 단어는 **float** 또는 **double** 값 (함수가 st (0)에서 반환 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)
