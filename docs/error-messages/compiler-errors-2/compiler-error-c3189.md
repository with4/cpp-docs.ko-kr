---
title: "컴파일러 오류 C3189 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3189
dev_langs:
- C++
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82bbe23b2dbbda71029e22ef8465a91a1889568b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3189"></a>컴파일러 오류 C3189
' typeid\<추상 선언 자 입력 >':이 구문은 더 이상 지원, 사용:: typeid 대신  
  
 사용 되지 않는 형식으로 [typeid](../../windows/typeid-cpp-component-extensions.md) 가 새 양식을 사용 하 여 사용 합니다.  
  
 다음 샘플에서는 C3189 오류가 생성 됩니다.  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```