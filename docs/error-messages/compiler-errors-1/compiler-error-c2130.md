---
title: "컴파일러 오류 C2130 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2130
dev_langs:
- C++
helpviewer_keywords:
- C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
caps.latest.revision: 10
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
ms.openlocfilehash: 0e6bcfc51ac27b060205d6191b5189e6d7071238
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2130"></a>컴파일러 오류 C2130
\#줄에 파일 이름을 'token'를 포함 하는 문자열이 있어야 하는데  
  
 선택적 파일 이름 토큰 다음 [#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` 문자열 이어야 합니다.  
  
 다음 샘플에서는 C2130을 생성합니다.  
  
```  
// C2130.cpp  
int main() {  
   #line 1000 test   // C2130  
   #line 1000 "test"   // OK  
}  
```
