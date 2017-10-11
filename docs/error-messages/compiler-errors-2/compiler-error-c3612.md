---
title: "컴파일러 오류 C3612 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3612
dev_langs:
- C++
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dd430c7dbdfae88d80e073fa9e624f123c41f366
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3612"></a>컴파일러 오류 C3612
'type': 클래스는 봉인된 클래스는 abstract 일 수 없습니다  
  
사용 하 여 정의 된 형식 `value` 기본적으로 봉인 됩니다. 기준의 모든 메서드를 구현 하지 않는 한이 클래스는 추상 및 합니다. 봉인된 추상 클래스는 기본 클래스에 있을 수 또는 그 인스턴스화할 수 있습니다.  
  
자세한 내용은 참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3612 오류가 생성 됩니다.  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```
