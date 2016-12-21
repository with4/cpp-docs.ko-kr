---
title: "안전한 라이브러리: C++ 표준 라이브러리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "안전한 라이브러리"
  - "안전한 라이브러리, 표준 C++ 라이브러리"
  - "안전한 표준 C++ 라이브러리"
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 안전한 라이브러리: C++ 표준 라이브러리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 C\+\+ 라이브러리를 포함하여 보안을 강화하기 위해 Visual C\+\+와 함께 제공되는 라이브러리의 여러 가지 기능이 향상되었습니다.  
  
 표준 C\+\+ 라이브러리의 일부 메서드는 버퍼 오버런이나 다른 코드 오류가 발생시킬 수 있기 때문에 잠재적으로 안전하지 않은 것으로 식별되었습니다. 이러한 메서드는 사용하지 않는 것이 좋으며, 이러한 메서드를 대체하기 위해 보다 안전한 새 메서드를 만들었습니다. 이러한 새 메서드는 모두 `_s`로 끝납니다.  
  
 반복기와 알고리즘도 보다 안전하게 만들기 위해 여러 가지 기능이 향상되었습니다. 자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md), [Debug Iterator Support](../standard-library/debug-iterator-support.md) 및 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.  
  
## 설명  
 다음 표에는 잠재적으로 안전하지 않은 표준 C\+\+ 라이브러리 메서드 및 보다 안전한 메서드가 나열되어 있습니다.  
  
|잠재적으로 안전하지 않은 메서드|보다 안전한 메서드|  
|-----------------------|----------------|  
|[basic\_string::copy](../Topic/basic_string::copy.md)|[basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md)|  
|[char\_traits::copy](../Topic/char_traits::copy.md)|[char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md)|  
  
 위의 잠재적으로 안전하지 않은 메서드 중 하나를 호출하거나 반복기를 잘못 사용하면 컴파일러에서 [컴파일러 경고 \(수준 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)를 생성합니다. 이러한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하세요.  
  
## 섹션 내용  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Checked Iterators](../standard-library/checked-iterators.md)  
  
 [Debug Iterator Support](../standard-library/debug-iterator-support.md)  
  
## 참고 항목  
 [STL 개요](../standard-library/cpp-standard-library-overview.md)