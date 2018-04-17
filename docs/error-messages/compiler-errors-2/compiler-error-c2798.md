---
title: 컴파일러 오류 C2798 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4336577d3f2d1174dadb370db6001e982e9035f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2798"></a>컴파일러 오류 C2798
'super::member' 모호합니다.  
  
 사용 하 여 참조 멤버를 포함 하는 다중 상속 된 구조 [super](../../cpp/super.md)합니다. 방법으로 오류를 해결할 수 있습니다.  
  
-   B1 또는 b 2 d 상속 목록에서 제거합니다.  
  
-   B1 또는 b 2의 데이터 멤버의 이름을 변경 합니다.  
  
 다음 샘플에서는 C2798 오류가 생성 됩니다.  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```