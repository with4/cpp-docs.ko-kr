---
title: "프로젝트 빌드 오류 PRJ0002 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0002"
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류 결과가 'command line'에서 반환되었습니다.  
  
 **속성 페이지** 대화 상자에 사용자가 입력한 내용을 통해 만들어진 ***command line*** 명령에서 오류 코드를 반환했지만 출력 창에는 내용이 표시되지 않습니다.  
  
 오류를 생성한 도구에 따라 이 오류에 대한 해결 방법이 달라집니다.  MIDL에서는 \/o\(출력 리디렉트\)를 정의한 경우 어떤 오류가 발생했는지 알 수 있습니다.  
  
 사용자 지정 빌드 단계나 빌드 이벤트같이 실패 조건에 대해 알려주지 않는 배치 파일 때문에 이 오류가 발생할 수 있습니다.