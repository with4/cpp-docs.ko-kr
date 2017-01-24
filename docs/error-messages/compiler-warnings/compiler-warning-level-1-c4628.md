---
title: "컴파일러 경고 (수준 1) C4628 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4628"
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\-Ze에는 digraph가 지원되지 않습니다.문자 시퀀스 'digraph'은\(는\) 'char'에 대한 대체 토큰으로 해석되지 않습니다.  
  
 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) 옵션이 지정된 경우에는 digraph가 지원되지 않습니다.  이 경고 다음에는 오류가 발생합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4628 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4628.cpp  
// compile with: /WX  
#pragma warning(default : 4628)  
int main()  
<%   // C4628 <% digraph for {  
}  
```