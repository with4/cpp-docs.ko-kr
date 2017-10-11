---
title: "컴파일러 오류 C3412 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3412
dev_langs:
- C++
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0e050e6d4aef2f9a51e6cc27e7b64b8f6cd8db3d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
