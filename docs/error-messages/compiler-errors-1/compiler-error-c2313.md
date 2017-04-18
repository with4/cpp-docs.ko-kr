---
title: "컴파일러 오류 C2313 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2313
dev_langs:
- C++
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
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
ms.openlocfilehash: cc79d4cbc61f4ca69f4a4f77400715a976c3d48e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2313"></a>컴파일러 오류 C2313
'type1': 참조('type2')에 의해 줄 number에서 catch되었습니다.  
  
 예외 형식에 두 개의 처리기가 있습니다. 두 번째 catch에 대한 형식이 첫 번째 형식에 대한 참조입니다.  
  
 다음 샘플에서는 C2313을 생성합니다.  
  
```  
// C2313.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
    try {  
        throw "ooops!";  
    }  
    catch( C& ) {}  
    catch( C ) {}   // C2313  
}  
```
