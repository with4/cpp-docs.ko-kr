---
title: 컴파일러 오류 C3672 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3672
dev_langs:
- C++
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aaea09d89c192a1820c2a384144ce758fde90476
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263949"
---
# <a name="compiler-error-c3672"></a>컴파일러 오류 C3672
의사 (pseudo) 소멸자 식은 함수 호출의 일부로 사용할 수 있습니다.  
  
 소멸자를 잘못 호출 했습니다.  자세한 내용은 참조 [소멸자](../../cpp/destructors-cpp.md)합니다.  
  
## <a name="example"></a>예제  
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