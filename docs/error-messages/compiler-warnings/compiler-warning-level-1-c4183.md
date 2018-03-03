---
title: "컴파일러 경고 (수준 1) C4183 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4183
dev_langs:
- C++
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec9462132c0640dc088dc89b36dd78dbfd057864
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4183"></a>컴파일러 경고 (수준 1) C4183
'identifier': 반환 형식이 없습니다. 'int'를 반환 하는 멤버 함수로 간주 됩니다.  
  
 멤버 함수는 클래스 또는 구조체에 대 한 인라인 정의는 반환 형식이 없습니다. 이 멤버 함수는 반환 형식이 기본 가정 `int`합니다.  
  
 다음 샘플에서는 C4183 오류가 생성 됩니다.  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```