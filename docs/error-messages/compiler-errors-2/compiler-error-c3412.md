---
title: "컴파일러 오류 C3412 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3412
dev_langs: C++
helpviewer_keywords: C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4f4716f64e4541ee1f4af7d3c57610a2d6f3843
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3412"></a>컴파일러 오류 C3412
'template': 현재 범위에서 템플릿을 특수화할 수 없습니다.  
  
 전역에 클래스 범위 또는 네임 스페이스 범위에서 템플릿을 특수화할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3412 오류가 발생 합니다.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```