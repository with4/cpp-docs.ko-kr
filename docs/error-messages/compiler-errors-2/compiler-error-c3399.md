---
title: "컴파일러 오류 C3399 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3399
dev_langs:
- C++
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a55a6d40d6d39b368c31a2716c14d05e0e49a78c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3399"></a>컴파일러 오류 C3399
'type': 제네릭 매개 변수의 인스턴스를 만들 때는 인수를 지정할 수 없습니다.  
  
 `gcnew()` 제약 조건을 지정할 때 제약 조건 형식이 매개 변수가 없는 생성자를 갖도록 지정합니다. 따라서 해당 형식을 인스턴스화하고 매개 변수를 전달하려고 하면 오류가 발생합니다.  
  
 참조 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + /cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3399를 생성합니다.  
  
```  
// C3399.cpp  
// compile with: /clr /c  
generic <class T>   
where T : gcnew()  
void f() {  
   T t = gcnew T(1);   // C3399  
   T t2 = gcnew T();   // OK  
}  
```