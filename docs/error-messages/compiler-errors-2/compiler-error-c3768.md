---
title: 컴파일러 오류 C3768 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3634ecf3eb1417095cce144706838113b5ad2a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3768"></a>컴파일러 오류 C3768
순수 관리 코드에서는 가상 vararg 함수의 주소를 가져올 수 없습니다.  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 로 컴파일할 때 `/clr:pure`를 가상의 주소를 가져올 수 없습니다 `vararg` 함수입니다.  
  
## <a name="example"></a>예제  

 다음 샘플에서는 C3768 오류가 생성 됩니다.  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```