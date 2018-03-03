---
title: "컴파일러 경고 (수준 4) C4268 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4268
dev_langs:
- C++
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b88e7c44099d49eb76d1bee9c68dd8a94413074a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4268"></a>컴파일러 경고(수준 4) C4268
'identifier': 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 된 'const' 정적/전역 데이터 개체를 0으로 채우기  
  
 A **const** 특수 한 클래스의 전역 또는 정적 인스턴스 컴파일러에서 생성 된 기본 생성자로 초기화 됩니다.  
  
## <a name="example"></a>예  
  
```  
// C4268.cpp  
// compile with: /c /LD /W4  
class X {  
public:  
   int m_data;  
};  
  
const X x1;   // C4268  
```  
  
 클래스의이 인스턴스는 대로 **const**, 값 `m_data` 변경할 수 없습니다.