---
title: 컴파일러 오류 C2790 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f1c90fed93666fad7513e2b4186a5baa2aa406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232819"
---
# <a name="compiler-error-c2790"></a>컴파일러 오류 C2790
'super':이 키워드는 클래스 멤버 함수의 본문 내 에서만 사용할 수 있습니다  
  
 이 오류 메시지가 표시 된 키워드를 사용 하 여 사용자가 하려고 할 경우 [super](../../cpp/super.md) 컨텍스트 외부에서 멤버 함수입니다.  
  
 다음 샘플에서는 C2790 오류가 생성 됩니다.  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```