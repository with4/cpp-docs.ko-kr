---
title: 컴파일러 오류 C2897 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2897
dev_langs:
- C++
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c3de4c0d3e6a93a783dfb660bc26f07be6fcacf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2897"></a>컴파일러 오류 C2897
소멸자/종료자 함수 템플릿일 수 없습니다.  
  
 소멸자 또는 종료자 오버 로드할 수 없습니다, 소멸자 (있음 소멸자의 집합을 정의)를 템플릿으로 선언 허용 되지 않습니다.  
  
 다음 샘플에서는 C2897 오류가 생성 됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2897 오류가 발생 합니다.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2897 오류가 발생 합니다.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```