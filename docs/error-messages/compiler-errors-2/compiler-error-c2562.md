---
title: "컴파일러 오류 C2562 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2562
dev_langs: C++
helpviewer_keywords: C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6bf1d7d9be8468ed0ccf65abea135992a50ac11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2562"></a>컴파일러 오류 C2562
'identifier': 값을 반환 하는 'void' 함수  
  
 으로 선언 된 함수 `void` 되었지만 값을 반환 합니다.  
  
 이 오류는 잘못 된 함수 프로토타입을 하 여 발생할 수 있습니다.  
  
 함수 선언에 반환 형식을 지정 하는 경우이 오류를 해결할 수 있습니다.  
  
 다음 샘플에서는 C2562 오류가 생성 됩니다.  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```