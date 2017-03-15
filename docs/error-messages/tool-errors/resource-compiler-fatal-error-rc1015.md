---
title: "리소스 컴파일러 심각한 오류 RC1015 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1015"
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 리소스 컴파일러 심각한 오류 RC1015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 포함 파일을 열 수 없습니다.  
  
 지정한 포함 파일이 없거나, 열 수 없거나, 찾을 수 없습니다.  
  
 환경 설정이 올바르며 파일에 대한 경로가 제대로 지정되었는지 확인하십시오.  리소스 컴파일러가 사용할 수 있는 파일 핸들 개수가 충분한지 확인하십시오.  또한 파일이 네트워크 드라이브에 있는 경우 해당 파일을 열 권한이 있는지 확인하십시오.  
  
 RC1015는 일반 속성 페이지 \-\> Resources \-\> 구성 속성에서 추가 포함 디렉터리로 지정된 디렉터리에 포함 파일이 있는 경우에도 발생할 수 있습니다. 포함 파일의 전체 경로를 지정하십시오.  
  
 자세한 내용은 기술 자료 문서 Q326987 : RC1015 Error When Using Resource View If the Include Path is Too Long을 참조하십시오.