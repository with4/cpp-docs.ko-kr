---
title: "LIBRARY | Microsoft Docs"
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
  - "LIBRARY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIBRARY .def 파일 문"
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LIBRARY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK에서 DLL을 만들도록 지시합니다.  해당 빌드에 .exp 파일이 사용되지 않은 경우에는 LINK에서 가져오기 라이브러리도 동시에 만듭니다.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## 설명  
 *library* 인수는 DLL의 이름을 지정합니다.  링커 옵션 [\/OUT](../../build/reference/out-output-file-name.md)을 사용하여 DLL의 출력 이름을 지정할 수도 있습니다.  
  
 BASE\=*address* 인수는 운영 체제가 해당 DLL을 로드하는 데 사용하는 기본 주소를 설정합니다.  이 인수는 기본 DLL 위치인 0x10000000을 재정의합니다.  기준 주소에 대한 자세한 내용은 [\/BASE](../../build/reference/base-base-address.md) 옵션의 설명 부분을 참조하십시오.  
  
 DLL을 빌드할 때에는 링커 옵션 [\/DLL](../../build/reference/dll-build-a-dll.md)을 반드시 사용해야 합니다.  
  
## 참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)