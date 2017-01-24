---
title: "SECTIONS(C/C++) | Microsoft Docs"
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
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SECTIONS .def 파일 문"
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# SECTIONS(C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로젝트의 출력 파일에 있는 섹션에 대한 액세스 지정자인 하나 이상의 `definitions`로 이루어진 섹션을 파생시킵니다.  
  
```  
SECTIONS  
definitions  
```  
  
## 설명  
 각 정의는 서로 다른 줄에 있어야 합니다.  `SECTIONS` 키워드는 첫 번째 정의와 같은 줄 또는 앞의 줄에 있을 수 있습니다.  .def 파일에는 하나 이상의 `SECTIONS` 문이 들어 있을 수 있습니다.  
  
 이 `SECTIONS` 문은 이미지 파일에 있는 하나 이상의 섹션에 대한 특성을 설정하며, 각 형식의 섹션에 대해 기본 특성을 재정의하는 데 사용될 수 있습니다.  
  
 `definitions`의 형식은 다음과 같습니다.  
  
 `.section_name specifier`  
  
 여기에서 `.section_name`은 프로그램 이미지의 섹션 이름이고 `specifier`는 다음과 같은 하나 이상의 액세스 한정자입니다.  
  
|한정자|설명|  
|---------|--------|  
|`EXECUTE`|해당 섹션을 실행할 수 있습니다.|  
|`READ`|데이터를 읽을 수 있습니다.|  
|`SHARED`|이미지를 로드하는 모든 프로세스에서 해당 섹션을 공유합니다.|  
|`WRITE`|데이터를 쓸 수 있습니다.|  
  
 식별자 이름은 공백으로 구분합니다.  예를 들면 다음과 같습니다.  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS`는 섹션 `definitions` 목록의 처음 부분을 표시합니다.  각 `definition`는 서로 다른 줄에 있어야 합니다.  `SECTIONS` 키워드는 첫 번째 `definition` 또는 이전 줄에서와 같은 줄이 될 수 있습니다.  .def 파일에는 하나 이상의 `SECTIONS` 문이 들어 있을 수 있습니다.  `SEGMENTS` 키워드는 `SECTIONS`에 대한 동의어로 지원됩니다.  
  
 이전 버전의 Visual C\+\+에서는 다음과 같은 형식을 지원했습니다.  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 `CLASS` 키워드는 호환성을 위해 지원되지만 무시됩니다.  
  
 이와 동일한 섹션 특성 지정 방법은 [\/SECTION](../../build/reference/section-specify-section-attributes.md) 옵션을 사용하는 것입니다.  
  
## 참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)