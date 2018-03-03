---
title: "컴파일러 오류 C2313 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2313
dev_langs:
- C++
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0c13aaa35f58a1ecc5ef51750416e86acb4429f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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