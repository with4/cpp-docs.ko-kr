---
title: "컨텍스트 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 662b540548c0594364bf11087c3b52420d29cf0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="attribute-contexts"></a>특성 컨텍스트
4 개의 기본 필드를 사용 하 여 c + + 특성을 설명할 수 있습니다: 대상에 적용 될 수 있습니다 (**에 적용 됩니다.**)는 인지 반복 하는 경우, (**Repeatable**), 필요한 (다른특성의존재여부 **필수 특성**), 및 이며 다른 특성과 호환 되지 않는 기능 (**잘못 된 특성이**). 이러한 필드는 각 특성의 참조 항목에 있는 해당 테이블에 나열 됩니다. 이러한 각 필드 아래에 설명 되어 있습니다.  
  
## <a name="applies-to"></a>적용 대상  
 이 필드는 지정된 된 특성에 대 한 법적 대상인 다른 c + + 언어 요소를 설명 합니다. 예를 들어, 특성에서 "클래스"를 지정 하는 경우는 **에 적용 됩니다.** 필드 나타냅니다는 특성 올바른 c + + 클래스에만 적용할 수 있습니다. 클래스의 멤버 함수에는 특성을 적용 하는 경우 구문 오류가 생깁니다.  
  
 자세한 내용은 참조 [용도별 특성](../windows/attributes-by-usage.md)합니다.  
  
## <a name="repeatable"></a>반복 가능  
 이 필드는 동일한 대상에 특성을 반복적으로 적용할 수 있는지 여부를 알려 줍니다. 특성의 대부분 재현이 불가능 합니다.  
  
## <a name="required-attributes"></a>필수 특성  
 이 필드 수 있어야 하는 다른 특성을 나열 제대로 작동 하려면 지정 된 특성 있음 (즉, 동일한 대상에 적용). 이 필드에 대 한 모든 항목을 특성에 대 한 일반적인 아닙니다.  
  
## <a name="invalid-attributes"></a>잘못 된 특성  
 이 필드는 지정 된 특성과 호환 되지 않는 다른 특성을 나열 합니다. 이 필드에 대 한 모든 항목을 특성에 대 한 일반적인 아닙니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 특성 참조](../windows/cpp-attributes-reference.md)