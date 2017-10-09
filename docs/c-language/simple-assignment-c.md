---
title: "단순 할당 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: c6f81732b4fccdac6ae0912b7617c28318da3e55
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="simple-assignment-c"></a>단순 할당 (C)
단순 할당 연산자는 오른쪽 피연산자를 왼쪽 피연산자에 할당합니다. 오른쪽 피연산자의 값은 할당 식의 형식으로 변환되며 왼쪽 피연산자로 지정된 개체에 저장된 값을 대체합니다. 할당에 대한 변환 규칙이 적용됩니다([할당 변환](../c-language/assignment-conversions.md) 참조).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 이 예제에서 `y`의 값은 **double** 형식으로 변환되어 `x`에 할당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 할당 연산자](../c-language/c-assignment-operators.md)
