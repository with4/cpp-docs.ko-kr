---
title: 컴파일러 오류 C3412 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3412
dev_langs:
- C++
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c5b2c86b91160eb7ae342b39ea6a63ffad364bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3412"></a>컴파일러 오류 C3412
'template': 현재 범위에서 템플릿을 특수화할 수 없습니다.  
  
 전역에 클래스 범위 또는 네임 스페이스 범위에서 템플릿을 특수화할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3412 오류가 발생 합니다.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```