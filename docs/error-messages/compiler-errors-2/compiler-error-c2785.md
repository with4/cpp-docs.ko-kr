---
title: "컴파일러 오류 C2785 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2785
dev_langs: C++
helpviewer_keywords: C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9587151175c593e4b1d9d30f45a19ce807c24990
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2785"></a>컴파일러 오류 C2785
'declaration1' 및 'declaration2'는 다른 반환 형식  
  
 함수 템플릿 특수화의 반환 형식이 기본 기능은 서식 파일의 반환 형식에서 다릅니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  일관성에 대 한 함수 템플릿의 모든 특수화를 확인 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2785 오류가 생성 됩니다.  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```