---
title: "클래스 범위가 있는 이름의 링크 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20e8204510f6f6e924e205b89dc9f95734b4b893
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linkage-in-names-with-class-scope"></a>클래스 범위가 있는 이름의 링크
다음 링크 규칙은 클래스 범위가 있는 이름에 적용됩니다.  
  
-   정적 클래스 멤버에는 외부 링크가 있습니다.  
  
-   클래스 멤버 함수에는 외부 링크가 있습니다.  
  
-   열거자 및 `typedef` 이름에는 링크가 없습니다.  
  
 **Microsoft 전용**  
  
-   `friend` 함수로 선언된 함수에는 외부 링크가 있어야 합니다. 정적 함수를 `friend`로 선언하면 오류가 발생합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)