---
title: "/RAWDATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rawdata"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RAWDATA dumpbin 옵션"
  - "원시 데이터"
  - "RAWDATA dumpbin 옵션"
  - "-RAWDATA dumpbin 옵션"
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /RAWDATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## 설명  
 이 옵션은 파일에서 각 섹션의 원시 콘텐츠를 표시합니다.  인수는 다음과 같이 표시 형식을 제어합니다.  
  
|인수|결과|  
|--------|--------|  
|1|기본값입니다.  콘텐츠는 16진수 바이트 값 및 인쇄가 가능할 경우 ASCII 문자로 표시됩니다.|  
|2|콘텐츠는 16진수 2바이트 값으로 표시됩니다.|  
|4|콘텐츠는 16진수 4바이트 값으로 표시됩니다.|  
|8|콘텐츠는 16진수 8바이트 값으로 표시됩니다.|  
|NONE|원시 데이터를 표시하지 않습니다.  이 인수는 \/ALL 출력을 제어하는 데 유용합니다.|  
|*숫자*|표시 줄에 줄 당 `number` 값 만큼의 너비를 설정합니다.|  
  
 [\/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)