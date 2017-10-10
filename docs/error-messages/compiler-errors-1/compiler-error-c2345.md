---
title: "컴파일러 오류 C2345 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2345
dev_langs:
- C++
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 372012b970ae277f3bb6854224bf4e432167abb3
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2345"></a>컴파일러 오류 C2345
align(value): 맞춤 값이 잘못되었습니다.  
  
 [align](../../cpp/align-cpp.md) 키워드에 허용 범위 외부의 값을 전달했습니다.  
  
 다음 코드에서는 C2345를 생성합니다.  
  
```  
// C2345.cpp  
// compile with: /c  
__declspec(align(0)) int a;   // C2345  
__declspec(align(1)) int a;   // OK  
```
