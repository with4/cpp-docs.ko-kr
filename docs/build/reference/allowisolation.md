---
title: "/ALLOWISOLATION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ALLOWISOLATION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION editbin 옵션"
  - "ALLOWISOLATION editbin 옵션"
  - "-ALLOWISOLATION editbin 옵션"
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /ALLOWISOLATION
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매니페스트 조회 동작을 지정합니다.  
  
## 구문  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## 설명  
 **\/ALLOWISOLATION**은 운영 체제에서 매니페스트 조회 및 로드가 수행되도록 합니다.  
  
 기본값은 **\/ALLOWISOLATION**입니다.  
  
 **\/ALLOWISOLATION:NO**는 매니페스트가 없는 것처럼 실행 파일이 로드되도록 지정하고, [EDITBIN 참조](../../build/reference/editbin-reference.md)이 선택적인 헤더의 `DllCharacteristics` 필드에 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 비트를 설정하도록 지정합니다.  
  
 실행 파일에 대해 격리가 비활성화되었으면 Windows 로더가 새로 생성되는 프로세스에 대해 응용 프로그램 매니페스트를 찾으려고 시도하지 않습니다.  실행 파일 자체에 매니페스트가 있거나 *executable\-name*.exe.manifest라는 이름의 매니페스트가 있더라도 새 프로세스에는 기본 활성화 컨텍스트가 포함되지 않습니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)   
 [\/ALLOWISOLATION\(매니페스트 조회\)](../../build/reference/allowisolation-manifest-lookup.md)   
 [매니페스트 파일 참조](http://msdn.microsoft.com/library/aa375632.aspx)