---
title: "컴파일러 오류 C2351 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2351
dev_langs: C++
helpviewer_keywords: C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97b6c52436d2850cfaaa1685692b7d974a6d8cad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2351"></a>컴파일러 오류 C2351
사용 되지 않는 c + + 생성자 초기화 구문입니다.  
  
 생성자는 새 스타일 초기화 목록에서 유일한 기본 클래스가 있는 경우에 각 직접 기본 클래스를 명시적으로 이름을 지정 해야 있습니다.  
  
 다음 샘플에서는 C2351 오류가 생성 됩니다.  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```