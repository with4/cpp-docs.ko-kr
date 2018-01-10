---
title: "컴파일러 경고 (수준 1) C4091 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4091
dev_langs: C++
helpviewer_keywords: C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9be40d65b657a7ac34fb105a2b1b16c702e4922c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4091"></a>컴파일러 경고 (수준 1) C4091
'keyword': 선언 된 변수가 없을 경우에 'type'의 왼쪽에 무시  
  
 컴파일러는 경우를 여기서 사용자 아마도 변수를 선언할 수 만들어졌으나 컴파일러는 변수를 선언할 수 없습니다.를 발견 했습니다.  
  
## <a name="example"></a>예  
 A `__declspec` 특성을 사용자 정의 형식 선언의 시작 부분에서 해당 형식의 변수에 적용 됩니다. C4091 선언 된 변수가 없음을 나타냅니다. 다음 샘플에서는 c4091 경고가 발생 합니다.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## <a name="example"></a>예  
 식별자 형식 정의 인 변수 이름 수도 없습니다. 다음 샘플에서는 c4091 경고가 발생 합니다.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```