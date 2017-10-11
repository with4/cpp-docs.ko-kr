---
title: "컴파일러 오류 C2286 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e1fca7ee629c35c083f6852a914e2ab62b4d5590
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2286"></a>컴파일러 오류 C2286
'identifier' 표현의 멤버의 포인터에 이미 '상속-' 선언이 무시 되었습니다.으로 설정 되었습니다.  
  
 클래스 멤버에 대 한 포인터 표현이 서로 존재합니다.  
  
 자세한 내용은 참조 [상속 키워드](../../cpp/inheritance-keywords.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2286을 생성합니다.  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```
