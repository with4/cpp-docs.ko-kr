---
title: 컴파일러 오류 C3748 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3748
dev_langs:
- C++
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de3d943db70b0e13b727f9c3e680f6cccc7f446e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274055"
---
# <a name="compiler-error-c3748"></a>컴파일러 오류 C3748
'interface': 관리 되는 인터페이스 이벤트를 발생 하지 않습니다  
  
 [__event](../../cpp/event.md) 키워드 내부 인터페이스에 표시할 수 없습니다.  
  
 다음 샘플에서는 C3748 오류가 생성 됩니다.  
  
```  
// C3748.cpp  
__interface I {  
// try the following line instead  
// struct I {  
   __event void f();   // C3748  
};  
  
int main() {  
}  
```