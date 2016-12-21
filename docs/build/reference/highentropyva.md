---
title: "/HIGHENTROPYVA | Microsoft Docs"
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
  - "/HIGHENTROPYVA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HIGHENTROPYVA editbin 옵션"
  - "HIGHENTROPYVA editbin 옵션"
  - "-HIGHENTROPYVA editbin 옵션"
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HIGHENTROPYVA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실행 가능 이미지가 높은 엔트로피 64비트 ASLR\(주소 공간 레이아웃 불규칙화\)을 지원하는지 여부를 지정합니다.  
  
```  
  
/HIGHENTROPYVA[:NO]  
  
```  
  
## 설명  
 이 옵션은 64비트 주소를 사용하는 ASLR이 지원되는지 여부를 나타내기 위해 .dll 파일 또는 .exe 파일의 헤더를 수정합니다.  실행 파일과 해당 파일이 종속된 모든 모듈에 대해 이 옵션을 설정하면 64비트 ASLR을 지원하는 운영 체제가 64비트 가상 주소 공간에서 임의 주소를 사용하여 로그 시에 실행 가능 이미지의 세그먼트 기준 주소를 다시 지정할 수 있습니다.  이처럼 큰 주소 공간을 사용하는 경우 공격자가 특정 메모리 영역의 위치를 추측하기가 어려워집니다.  
  
 기본적으로 링커는 64비트 실행 가능 이미지에 대해 이 옵션을 설정합니다.  이 옵션을 설정하려면 [\/DYNAMICBASE](../../build/reference/dynamicbase.md) 옵션도 설정해야 합니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)   
 [\/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows ISV 소프트웨어 보안 방어 \(영문\)](http://msdn.microsoft.com/library/bb430720.aspx)