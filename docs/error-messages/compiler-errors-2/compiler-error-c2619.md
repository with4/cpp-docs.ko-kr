---
title: 컴파일러 오류 C2619 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2619
dev_langs:
- C++
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c39337ee76f015a4b7afa25ddd9176c6edb9501c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2619"></a>컴파일러 오류 C2619
'identifier': 익명 구조체 또는 집합체에는 정적 데이터 멤버가 허용되지 않습니다.  
  
 익명 구조체 또는 공용 구조체의 멤버는 `static`으로 선언됩니다.  
  
 다음 샘플에서는 C2619 오류가 발생하는 경우 및 static 키워드를 제거하여 오류를 해결하는 방법을 보여 줍니다.  
  
```  
// C2619.cpp  
int main() {  
   union { static int j; };  // C2619  
   union { int j; };  // OK  
}  
```