---
title: 컴파일러 경고 (수준 2) C4285 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4366142c14ec77c1c344312e50e7295c71ca93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4285"></a>컴파일러 경고(수준 2) C4285
'identifier:: operator->'의 반환 형식은 중 위 표기법을 사용 하 여 적용할 경우 재귀적입니다.  
  
 지정 된 **operator-> ()** 함수에 대 한 형식을 반환할 수 없습니다 정의 된 또는 정의 된 형식에 대 한 참조입니다.  
  
 다음 샘플에서는 C4285 오류가 생성 됩니다.  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```