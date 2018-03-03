---
title: "컴파일러 오류 C3194 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3194
dev_langs:
- C++
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5bb89c346d1e60d3575798c9cd7e35700328bea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3194"></a>컴파일러 오류 C3194
'member': 값 형식 할당 연산자를 사용할 수 없습니다  
  
 예: 복사 생성자 또는 복사 할당 연산자는 컴파일러에 의해 자동 호출을 필요로 하는 특수 멤버 함수는 값 클래스 내에서 지원 되지 않습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3194 오류가 발생 합니다.  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```