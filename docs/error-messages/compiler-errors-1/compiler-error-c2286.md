---
title: 컴파일러 오류 C2286 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ddfb523252572fb985b660f1d4dbf5b1d790df1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171928"
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