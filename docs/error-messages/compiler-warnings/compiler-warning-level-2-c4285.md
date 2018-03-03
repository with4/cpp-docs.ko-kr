---
title: "컴파일러 경고 (수준 2) C4285 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85f7904eb3a570b8f348503277117167a624a0d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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