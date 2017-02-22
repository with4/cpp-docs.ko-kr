---
title: "/DYNAMICBASE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dynamicbase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE editbin 옵션"
  - "DYNAMICBASE editbin 옵션"
  - "-DYNAMICBASE editbin 옵션"
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /DYNAMICBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ASLR\(주소 공간 레이아웃 불규칙화\)를 사용해서 로드 시 실행 가능 이미지를 임의로 릴리스할 수 있는지 여부를 지정합니다.  
  
## 구문  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## 설명  
 기본적으로 링커는 **\/DYNAMICBASE** 옵션을 설정합니다.  
  
 이 옵션은 실행 가능 이미지의 헤더를 수정해서 로드 시 로더가 이미지의 기준 주소를 임의로 다시 지정할 수 있는지 여부를 나타냅니다.  
  
 ASLR은 Windows Vista, Windows Server 2008, Windows 7, Windows 8 및 Windows Server 2012에서 지원됩니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)   
 [Windows ISV 소프트웨어 보안 방어 \(영문\)](http://msdn.microsoft.com/library/bb430720.aspx)