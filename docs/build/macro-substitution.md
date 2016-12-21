---
title: "매크로 대체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "매크로, NMAKE"
  - "NMAKE 프로그램, 매크로 대체"
  - "NMAKE의 대체 매크로"
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 매크로 대체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*macroname*이 호출되면 정의 문자열의 각 *string1*은 *string2*로 바뀝니다.  
  
## 구문  
  
```  
$(macroname:string1=string2)  
```  
  
## 설명  
 매크로 대체는 대\/소문자를 구분하고 리터럴 문자이므로 *string1*과 *string2*는 매크로를 호출할 수 없습니다.  매크로를 대체해도 원래 정의는 수정되지 않습니다.  [$$@](../build/filename-macros.md)를 제외한 미리 정의된 모든 매크로의 텍스트는 대체할 수 있습니다.  
  
 콜론 앞에는 공백이나 탭이 올 수 없고 콜론 뒤에 오는 공백이나 탭은 리터럴 문자로 해석됩니다.  *string2*가 null인 경우 매크로의 정의 문자열에서 모든 *string1*이 삭제됩니다.  
  
## 참고 항목  
 [NMAKE 매크로 사용](../build/using-an-nmake-macro.md)