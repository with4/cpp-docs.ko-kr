---
title: "/INTEGRITYCHECK | Microsoft Docs"
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
  - "/INTEGRITYCHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INTEGRITYCHECK editbin 옵션"
  - "INTEGRITYCHECK editbin 옵션"
  - "-INTEGRITYCHECK editbin 옵션"
ms.assetid: 2a293705-4396-421b-a5a5-693b4b867a85
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /INTEGRITYCHECK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로드 시 이진 이미지의 디지털 신호를 확인해야 함을 지정합니다.  
  
```  
  
/INTEGRITYCHECK[:NO]  
  
```  
  
## 설명  
 DLL 파일 또는 실행 파일의 헤더에서 이 옵션은 메모리 관리자가 Windows에서 이미지를 로드하기 위해 디지털 서명 확인이 필요한 플래그를 설정합니다.  Windows Vista 이전의 windows 버전은 이 플래그를 무시합니다.  이 옵션은 커널 모드 코드를 구현하는 64비트 DLL용으로 설정되어야 하며, 모든 장치 드라이버에 대해 권장됩니다.  자세한 내용은 MSDN 웹 사이트에서 [커널 모드 코드 서명 연습](http://go.microsoft.com/fwlink/?linkid=237093)을 참조하십시오.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)