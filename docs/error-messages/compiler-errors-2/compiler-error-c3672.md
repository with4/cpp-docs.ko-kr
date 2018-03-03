---
title: "컴파일러 오류 C3672 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3672
dev_langs:
- C++
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b47d6a6f565ccd569c68a500974a0e185b1da21a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3672"></a>컴파일러 오류 C3672
의사 (pseudo) 소멸자 식은 함수 호출의 일부로 사용할 수 있습니다.  
  
 소멸자를 잘못 호출 했습니다.  자세한 내용은 참조 [소멸자](../../cpp/destructors-cpp.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3672 오류가 발생 합니다.  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```