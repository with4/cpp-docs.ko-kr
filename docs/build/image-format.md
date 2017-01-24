---
title: "이미지 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 이미지 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

실행 가능 이미지 형식은 PE32\+입니다.  실행 가능 이미지\(DLL 및 EXE\)의 최대 크기는 2기가바이트로 제한되어 있으므로 정적 이미지 데이터를 처리하기 위해 32비트 치환된 상대 주소를 사용할 수 있습니다.  이 데이터에는 가져오기 주소 테이블, 문자열 제약 조건, 정적 전역 데이터 등이 포함됩니다.  
  
## 참고 항목  
 [x64 소프트웨어 규칙](../build/x64-software-conventions.md)