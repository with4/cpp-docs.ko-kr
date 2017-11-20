---
title: "컴파일러 오류 C2897 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2897
dev_langs: C++
helpviewer_keywords: C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d3aa9ae6c79d3320104d9689f82b894cf2b76d9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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