---
title: "지연 로드된 가져오기 덤프 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "지연 로드 가져오기"
  - "지연 로드 가져오기, 덤프하기"
  - "가져오기(지연 로드)"
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 지연 로드된 가져오기 덤프
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지연 로드된 가져오기는 [dumpbin \/IMPORTS](../../build/reference/imports-dumpbin.md)를 사용하여 덤프될 수 있으며 표준 가져오기와 약간 다른 내용을 표시합니다.  지연 로드된 가져오기는 자체의 \/imports 덤프 섹션으로 분리되고 지연 로드된 가져오기라는 레이블이 명시적으로 붙습니다.  이미지에 언로드 정보가 있으면 해당 내용이 기록되며  바인드 정보가 있으면 대상 DLL의 타임스탬프와 날짜 스탬프가 바인딩된 가져오기 주소와 함께 기록됩니다.  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)