---
title: 컴파일러 오류 C3834 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3834
dev_langs:
- C++
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1259ca2126211d6e91ed230a81959810b6427180
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267716"
---
# <a name="compiler-error-c3834"></a>컴파일러 오류 C3834
명시적으로 잘못 캐스팅 했습니다 고정 포인터; 대신 고정된 된 지역 변수를 사용 합니다.  
  
 고정 포인터로 명시적 캐스트는 허용 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3834 오류가 발생 합니다.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  
