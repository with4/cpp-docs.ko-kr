---
title: "컴파일러 경고 (수준 3) C4159 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f335dedddd3e5c948a009f49c925c7d59901de1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4159"></a>컴파일러 경고 (수준 3) C4159
\#pragma pragma(pop,...): 이전에 푸시한 'identifier' 식별자를 팝 했습니다  
  
 소스 코드에 포함 한 **푸시** 는 pragma에 대 한 식별자를 사용 하 여 명령을 뒤는 **pop** 식별자 없이 명령입니다. 결과적으로, ***식별자*** 꺼낸, 및 후속 사용은 ***식별자*** 예기치 않은 동작이 발생할 수 있습니다.  
  
 이 경고를 방지 하려면에 식별자를 제공는 **pop** 명령입니다. 예:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```