---
title: "링커 도구 경고 LNK4105 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4105"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4105"
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 경고 LNK4105
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'option' 옵션에 지정된 인수가 없습니다. 옵션이 무시됩니다.  
  
 이 경고는 [\/LIBPATH](../../build/reference/libpath-additional-libpath.md) 옵션이 설정된 경우에만 발생합니다.  이 옵션으로 지정된 디렉터리가 없으면 링커가 옵션을 무시하며 이 경고 메시지를 발생시킵니다.  
  
 기존 환경 라이브러리 설정을 재정의하지 않아도 되는 경우에는 링커 명령줄에서 \/LIBPATH 옵션을 제거하십시오.  라이브러리에 대한 대체 검색 경로를 사용하려면 \/LIBPATH 옵션 다음에 대체 경로를 지정하십시오.  
  
## 예제  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 위의 구문을 사용하면 링커가 필수 라이브러리를 기본 위치에서 검색하기 전에 `c:\filepath\lib`에서 검색합니다.