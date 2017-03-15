---
title: "Attribute Contexts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], contexts"
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Attribute Contexts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

4 개의 기본 필드를 사용 하 여 C\+\+ 특성을 설명 있습니다: 대상이 적용할 수 있습니다 \(**적용 대상**\), 반복 되는 경우 \(**여기서 반복 성**은\)에서 필요한 다른 특성의 존재 \(**필수 특성**\), 및 다른 특성을 갖는 비 호환성 \(**잘못 된 특성**\).  이러한 필드는 해당 표를 각 특성 참조 항목에 나열 됩니다.  각이 필드는 다음과 같습니다.  
  
## 적용 대상  
 이 필드가 지정 된 특성에 대 한 법적 대상의 다른 C\+\+ 언어 요소를 설명 합니다.  예를 들어,에서는 "클래스"는 특성을 지정 하는 경우는  **적용 대상** 필드에서이 나타내는 특성을 올바른 C\+\+ 클래스에만 적용할 수 있습니다.  특성 클래스의 멤버 함수에 적용 되는 경우 구문 오류가 반환 됩니다.  
  
 자세한 내용은  [특성을 사용 하 여](../windows/attributes-by-usage.md).  
  
## 반복 가능  
 이 필드 특성 반복적으로 동일한 대상에 적용할지 여부를 나타냅니다.  대부분의 속성이 반복 되지 않습니다.  
  
## 필수 특성  
 해야 할 다른 속성이 필드 목록 \(즉, 동일한 대상으로 적용 됨\) 선물 제대로 작동 하려면 지정 된 특성입니다.  이 필드에 대 한 모든 항목에는 속성에 대 한 흔하지 않습니다.  
  
## 잘못 된 특성  
 이 필드에 지정 된 특성이 호환 되지 않는 다른 특성을 나열 합니다.  이 필드에 대 한 모든 항목에는 속성에 대 한 흔하지 않습니다.  
  
## 참고 항목  
 [C\+\+ Attributes Reference](../windows/cpp-attributes-reference.md)