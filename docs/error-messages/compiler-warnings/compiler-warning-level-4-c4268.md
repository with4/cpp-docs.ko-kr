---
title: 컴파일러 경고 (수준 4) C4268 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4268
dev_langs:
- C++
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bef62649af39df950c3966ef93dddb6c71ec2fd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4268"></a>컴파일러 경고(수준 4) C4268
'identifier': 컴파일러에서 생성 된 기본 생성자를 사용 하 여 초기화 된 'const' 정적/전역 데이터 개체를 0으로 채우기  
  
 A **const** 특수 한 클래스의 전역 또는 정적 인스턴스 컴파일러에서 생성 된 기본 생성자로 초기화 됩니다.  
  
## <a name="example"></a>예제  
  
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