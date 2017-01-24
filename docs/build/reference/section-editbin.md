---
title: "/SECTION(EDITBIN) | Microsoft Docs"
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
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION editbin 옵션"
  - "섹션의 맞춤 문자"
  - "SECTION editbin 옵션"
  - "-SECTION editbin 옵션"
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SECTION(EDITBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## 설명  
 이 옵션은 섹션의 개체 파일을 컴파일하거나 링크할 때 설정한 특성을 재정의하여 섹션 특성을 변경합니다.  
  
 콜론\(**:**\) 다음에 섹션의 *name*을 지정합니다.  섹션 이름을 변경하려면 *name* 다음에 등호\(\=\)와 섹션의 *newname*을 입력합니다.  
  
 섹션의 `attributes`를 설정하거나 변경하려면 쉼표\(**,**\) 다음에 하나 이상의 특성 문자를 지정합니다.  특성을 부정하려면 특성 문자 앞에 느낌표\(\!\)를 붙입니다.  다음 문자는 메모리 특성을 지정합니다.  
  
|특성|설정값|  
|--------|---------|  
|c|코드|  
|d|discardable|  
|e|executable|  
|i|initialized data|  
|k|cached virtual memory|  
|m|link remove|  
|o|link info|  
|p|paged virtual memory|  
|r|read|  
|s|shared|  
|u|uninitialized data|  
|w|write|  
  
 *alignment*를 제어하려면 **A** 문자 다음에 바이트 단위로 맞춤 크기를 설정하는 다음과 같은 문자 중 하나를 지정합니다.  
  
|문자|바이트 단위 맞춤 크기|  
|--------|------------------|  
|1|1|  
|2|2|  
|4|4|  
|8|8|  
|p|16|  
|t|32|  
|s|64|  
|x|맞춤 안 함|  
  
 여러 개의 `attributes` 및 *alignment* 문자는 공백 없이 하나의 문자열로 지정합니다.  문자는 대\/소문자를 구분하지 않습니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)