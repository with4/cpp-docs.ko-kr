---
title: 컴파일러 오류 C2628 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2628
dev_langs:
- C++
helpviewer_keywords:
- C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3f9813f103f59e61093ab82366e50a7ef6dae46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2628"></a>컴파일러 오류 C2628
'type1' 뒤에 'type2'은 사용할 수 없습니다 (했는지 확인 한 ';'?)  
  
 세미콜론 없을 수 있습니다.  
  
 다음 샘플에서는 C2628 오류가 생성 됩니다.  
  
```  
// C2628.cpp  
class CMyClass {}  
int main(){}   // C2628 error  
```  
  
 해결 방법:  
  
```  
// C2628b.cpp  
class CMyClass {};  
int main(){}  
```