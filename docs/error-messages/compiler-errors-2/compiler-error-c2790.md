---
title: "컴파일러 오류 C2790 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b10da64605743612a4d5522b5c19d1f2029ced8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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