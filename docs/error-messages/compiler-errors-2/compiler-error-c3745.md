---
title: 컴파일러 오류 C3745 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3745
dev_langs:
- C++
helpviewer_keywords:
- C3745
ms.assetid: 1e64aec5-7e53-47e5-bc7d-3905230cfc66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d97177fb51aecf668a041e43218ccb342f6c15b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265738"
---
# <a name="compiler-error-c3745"></a>컴파일러 오류 C3745
'function':만 이벤트가 발생할 수 있는' '  
  
 정의 된 함수에만 [__event](../../cpp/event.md) 키워드에 전달 될 수는 [__raise](../../cpp/raise.md) 키워드입니다.  
  
 다음 샘플에서는 C3745 오류가 생성 됩니다.  
  
```  
// C3745.cpp  
struct E {  
   __event void func();  
   void func(int) {  
   }  
  
   void func2() {  
   }  
  
   void bar() {  
      __raise func();  
      __raise func(1);   // C3745  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func();  
   __raise e.func(1);   // C3745  
   __raise e.func2();   // C3745  
}  
```