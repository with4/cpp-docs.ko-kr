---
title: "컴파일러 오류 C2628 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2628
dev_langs:
- C++
helpviewer_keywords:
- C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 60fd4e45b19423e32b7a5973b8bdfad34b75bcc6
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
