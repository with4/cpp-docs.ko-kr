---
title: "명령줄 오류 D8016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D8016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8016"
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 명령줄 오류 D8016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'option1'과\(와\) 'option2' 명령줄 옵션이 호환되지 않습니다.  
  
 이들 명령줄 옵션을 함께 지정할 수 없습니다.  
  
 CL 같은 환경 변수에서 옵션 사양을 확인하십시오.  
  
 **\/clr**은 **\/EHa**를 암시하며 다른 **\/EH** 컴파일러 옵션을 **\/clr**과 함께 지정할 수 없습니다.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0 프로젝트로 업데이트한 후에 D8016이 발생할 수도 있습니다. 프로젝트 업데이트 마법사는 프로젝트의 각 소스 코드 파일에 대해 **\/RTC**를 활성화하므로 프로젝트의 **\/RTC** 설정이 재정의될 수 있습니다.  이 문제를 해결하려면 프로젝트의 각 소스 코드 파일에 대한 **\/RTC** 설정을 기본 설정으로 변경하여 **\/RTC**  프로젝트 설정이 각 파일에 적용되도록 합니다.  
  
 **\/RTC** 프로젝트 설정 변경에 대한 자세한 내용은 [\/RTC\(런타임 오류 검사\)](../../build/reference/rtc-run-time-error-checks.md)를 참조하십시오.