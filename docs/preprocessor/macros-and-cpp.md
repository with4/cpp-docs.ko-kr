---
title: "매크로 및 c + + | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7af092d31fb4495be47c88aaaf8830cc05db2bc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="macros-and-c"></a>매크로 및 C++
C++는 새로운 기능을 제공하며 그 중 일부는 ANSI C 전처리기에서 제공하는 기능을 대신합니다. 이 새로운 기능으로 형식이 더욱 안전해지고 효과적으로 언어를 예측할 수 있습니다.  
  
-   C + +에서는로 선언 된 개체 **const** 상수 식에 사용할 수 있습니다. 형식 및 값 정보가 있는 상수와 디버거에서 기호로 표시된 열거형이 있는 상수를 프로그램에서 선언할 수 있습니다. 전처리기 `#define` 지시문을 사용하여 상수를 정의하는 것으로는 충분하지 않습니다. 저장소가 할당 되지 않으므로는 **const** 프로그램에 해당 주소를 사용 하는 식을 발견 되는 경우가 아니면 개체입니다.  
  
-   C ++ 인라인 함수 기능은 함수 형식 매크로를 대신합니다. 인라인 함수를 사용하면 매크로에 비해 다음과 같은 이점이 있습니다.  
  
    -   형식 안전성. 인라인 함수는 일반 함수와 똑같은 함수 검사를 받습니다. 매크로는 형식이 안전하지 않습니다.  
  
    -   의도하지 않은 결과가 생기는 인수를 올바르게 처리. 인라인 함수는 함수 본문을 입력하기 전에 식을 인수로 계산하므로 의도하지 않은 결과를 가진 식이 안전성을 유지할 수 있습니다.  
  
 인라인 함수에 대 한 자세한 내용은 참조 하십시오. [인라인, __inline, \__forceinline](../cpp/inline-functions-cpp.md)합니다.  
  
 이전 버전과의 호환성을 위해 ANSI C 및 이전의 C++ 사양에 있는 모든 전처리기 기능이 Microsoft C++에 대해 유지됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [미리 정의 된 매크로](../preprocessor/predefined-macros.md)   
 [매크로(C/C++)](../preprocessor/macros-c-cpp.md)