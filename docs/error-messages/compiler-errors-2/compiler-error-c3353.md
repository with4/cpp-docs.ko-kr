---
title: "컴파일러 오류 C3353 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 051300b1c670381c0450b373058644fc5a84e7d4
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3353"></a>컴파일러 오류 C3353
'delegate': 대리자는 전역 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에서만 만들어질 수 있습니다.  
  
 대리자를 사용 하 여 선언 된 [위임](../../windows/delegate-cpp-component-extensions.md) 키워드를 전역 범위에서 선언할 수 있습니다.  
  
 다음 샘플에서는 C3353을 생성합니다.  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```
